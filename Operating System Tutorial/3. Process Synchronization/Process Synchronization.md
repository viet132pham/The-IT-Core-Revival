# Process Synchronization trong Hệ điều hành

## Tổng quan

Process Synchronization (Đồng bộ hóa tiến trình) là một khái niệm quan trọng trong hệ điều hành, giải quyết các vấn đề phát sinh khi nhiều tiến trình cùng truy cập và thao tác trên dữ liệu chia sẻ. Đây là một trong những thành phần cốt lõi của hệ điều hành để đảm bảo hoạt động đúng đắn của hệ thống đa nhiệm.

## Khái niệm cơ bản

### Race Condition (Tình trạng đua)

Race condition xảy ra khi hai hay nhiều tiến trình cùng truy cập và thao tác trên dữ liệu chia sẻ đồng thời, và kết quả cuối cùng phụ thuộc vào thứ tự thực hiện các thao tác đó.

Ví dụ: Hai tiến trình cùng cập nhật một biến toàn cục. Tiến trình 1 đọc giá trị, tăng lên 1 và ghi lại. Tiến trình 2 cũng làm tương tự. Nếu các thao tác này xen kẽ nhau, kết quả cuối cùng có thể không chính xác.

### Critical Section (Miền găng)

Critical Section là đoạn mã mà trong đó tiến trình truy cập vào tài nguyên chia sẻ. Để tránh race condition, cần đảm bảo rằng khi một tiến trình đang thực thi trong critical section của nó, không có tiến trình nào khác được thực thi trong critical section của chúng.

Một giải pháp cho vấn đề critical section phải thỏa mãn ba điều kiện sau:

1. **Mutual Exclusion (Loại trừ tương hỗ)**: Nếu tiến trình Pi đang thực thi trong critical section, thì không có tiến trình nào khác được thực thi trong critical section của chúng.

2. **Progress (Tiến triển)**: Nếu không có tiến trình nào đang thực thi trong critical section và có các tiến trình muốn vào critical section, thì việc quyết định tiến trình nào được vào critical section tiếp theo chỉ có thể được thực hiện bởi các tiến trình không đang thực thi trong remainder section (phần còn lại), và quyết định này không thể bị trì hoãn vô hạn.

3. **Bounded Waiting (Chờ đợi có giới hạn)**: Phải có giới hạn về số lần mà các tiến trình khác được phép vào critical section sau khi một tiến trình đã yêu cầu vào critical section và trước khi yêu cầu đó được chấp nhận.

## Các giải pháp đồng bộ hóa

### 1. Semaphores (Đèn hiệu)

Semaphore là một biến nguyên được sử dụng để kiểm soát việc truy cập vào tài nguyên chia sẻ trong môi trường đa luồng. Semaphore có hai thao tác cơ bản:

- **wait()** (hay P()): Giảm giá trị của semaphore xuống 1. Nếu giá trị trở thành âm, tiến trình sẽ bị block.
- **signal()** (hay V()): Tăng giá trị của semaphore lên 1. Nếu giá trị không dương, một tiến trình đang chờ đợi sẽ được unblock.

Có hai loại semaphore:
- **Binary Semaphore**: Có giá trị 0 hoặc 1, tương tự như mutex.
- **Counting Semaphore**: Có thể nhận giá trị nguyên không âm bất kỳ.

```c
wait(S) {
    while (S <= 0); // Busy waiting
    S--;
}

signal(S) {
    S++;
}
```

### 2. Mutex Locks (Khóa loại trừ tương hỗ)

Mutex là một cơ chế đơn giản hơn so với semaphore, được sử dụng để cung cấp loại trừ tương hỗ. Một mutex có hai trạng thái: locked và unlocked.

```c
acquire() {
    while (!available); // Busy waiting
    available = false;
}

release() {
    available = true;
}
```

### 3. Monitors (Bộ giám sát)

Monitor là một cấu trúc ngôn ngữ lập trình cấp cao hơn semaphore, cung cấp các cơ chế đồng bộ hóa. Monitor đảm bảo rằng chỉ một tiến trình có thể hoạt động trong monitor tại một thời điểm.

Monitor bao gồm:
- Các biến chia sẻ
- Các thủ tục có thể được gọi bởi các tiến trình khác
- Mã khởi tạo
- Condition variables cho việc đồng bộ hóa

### 4. Condition Variables (Biến điều kiện)

Condition variables được sử dụng trong monitors để chờ đợi một điều kiện cụ thể trở thành true. Có hai thao tác chính:

- **wait()**: Tiến trình sẽ bị block cho đến khi được signal.
- **signal()**: Báo hiệu cho một tiến trình đang chờ đợi trên condition variable.

## Các vấn đề kinh điển trong đồng bộ hóa

### 1. Producer-Consumer Problem (Vấn đề người sản xuất - người tiêu dùng)

Vấn đề này liên quan đến hai loại tiến trình: producer (tạo ra dữ liệu) và consumer (tiêu thụ dữ liệu). Họ chia sẻ một buffer có kích thước cố định.

Điều kiện đồng bộ hóa:
- Producer không thể thêm dữ liệu khi buffer đầy.
- Consumer không thể lấy dữ liệu khi buffer trống.
- Không thể truy cập buffer đồng thời.

### 2. Readers-Writers Problem (Vấn đề người đọc - người ghi)

Vấn đề này liên quan đến việc đồng bộ hóa giữa nhiều tiến trình đọc và ghi dữ liệu trên một tài nguyên chia sẻ.

Điều kiện đồng bộ hóa:
- Nhiều reader có thể đọc đồng thời.
- Chỉ một writer có thể ghi tại một thời điểm.
- Không thể đọc và ghi đồng thời.

### 3. Dining Philosophers Problem (Vấn đề các triết gia ăn tối)

Năm triết gia ngồi quanh bàn, mỗi người có một đĩa mì trước mặt và một đũa giữa mỗi cặp triết gia kề nhau. Mỗi triết gia cần hai đũa để ăn.

Vấn đề là làm thế nào để triết gia lấy đũa mà không gây ra deadlock (tất cả đều nắm một đũa và đợi đũa còn lại).

## Deadlock (Bế tắc)

Deadlock là tình huống hai hoặc nhiều tiến trình chờ đợi lẫn nhau để giải phóng tài nguyên mà chúng đang giữ.

### Điều kiện cần cho deadlock:

1. **Mutual Exclusion**: Ít nhất một tài nguyên phải được giữ ở chế độ không chia sẻ.
2. **Hold and Wait**: Tiến trình giữ ít nhất một tài nguyên và đang chờ để có được tài nguyên bổ sung.
3. **No Preemption**: Tài nguyên không thể bị thu hồi từ tiến trình đang giữ nó.
4. **Circular Wait**: Tồn tại một tập hợp các tiến trình đang chờ đợi, trong đó mỗi tiến trình chờ tài nguyên đang được giữ bởi tiến trình tiếp theo trong tập hợp.

### Phương pháp xử lý deadlock:

1. **Deadlock Prevention**: Đảm bảo ít nhất một trong bốn điều kiện cần không thỏa mãn.
2. **Deadlock Avoidance**: Yêu cầu hệ điều hành biết trước thông tin về tài nguyên mà mỗi tiến trình sẽ yêu cầu.
3. **Deadlock Detection and Recovery**: Cho phép deadlock xảy ra, sau đó phát hiện và khôi phục.
4. **Ignore the Problem**: Giả vờ rằng deadlock không bao giờ xảy ra (phương pháp đà đà).

## Starvation (Đói tài nguyên)

Starvation là tình huống trong đó một tiến trình không bao giờ được cấp phát tài nguyên mà nó cần, mặc dù tài nguyên đó không bị deadlock. Điều này thường xảy ra do chính sách phân phối tài nguyên không công bằng.

## Priority Inversion (Đảo ngược ưu tiên)

Priority inversion xảy ra khi một tiến trình ưu tiên cao phải chờ một tiến trình ưu tiên thấp hoàn thành công việc của nó. Điều này có thể xảy ra khi tiến trình ưu tiên thấp đang giữ một tài nguyên mà tiến trình ưu tiên cao cần.

## Kết luận

Process Synchronization là một lĩnh vực quan trọng trong hệ điều hành, giải quyết các vấn đề phát sinh khi nhiều tiến trình cùng hoạt động và chia sẻ tài nguyên. Các giải pháp như semaphore, mutex, monitor và condition variables giúp điều phối hoạt động của các tiến trình, tránh race condition và đảm bảo tính toàn vẹn của dữ liệu chia sẻ.

Hiểu biết về các vấn đề kinh điển như Producer-Consumer, Readers-Writers và Dining Philosophers cũng như các khái niệm liên quan như deadlock, starvation và priority inversion là nền tảng quan trọng cho việc thiết kế hệ thống đa nhiệm hiệu quả và ổn định.
# Deadlock trong Hệ điều hành

## Khái niệm cơ bản về Deadlock

Deadlock (bế tắc) là một tình trạng trong hệ thống đa nhiệm khi hai hoặc nhiều tiến trình bị chặn vĩnh viễn, mỗi tiến trình đang chờ một tài nguyên đang bị giữ bởi tiến trình khác. Trong tình huống này, không có tiến trình nào có thể tiếp tục thực thi và hệ thống sẽ bị treo nếu không có sự can thiệp từ bên ngoài.

### Ví dụ minh họa

Giả sử có hai tiến trình P1 và P2, và hai tài nguyên R1 và R2:
- P1 giữ R1 và cần R2 để tiếp tục.
- P2 giữ R2 và cần R1 để tiếp tục.

Kết quả: Cả hai tiến trình đều bị chặn, chờ đợi tài nguyên mà tiến trình kia đang giữ, tạo thành một vòng tròn chờ đợi không thể phá vỡ.

## Điều kiện Coffman

Deadlock xảy ra khi bốn điều kiện Coffman sau đây xuất hiện đồng thời:

1. **Mutual Exclusion (Loại trừ tương hỗ)**:
   - Ít nhất một tài nguyên phải ở chế độ không chia sẻ được, chỉ một tiến trình có thể sử dụng tài nguyên tại một thời điểm.

2. **Hold and Wait (Giữ và chờ đợi)**:
   - Các tiến trình đang giữ tài nguyên đồng thời chờ đợi các tài nguyên bổ sung.

3. **No Preemption (Không có đoạt quyền)**:
   - Tài nguyên không thể bị lấy đi từ tiến trình đang sử dụng cho đến khi tiến trình đó tự giải phóng.

4. **Circular Wait (Chờ đợi vòng tròn)**:
   - Tồn tại một chuỗi các tiến trình {P1, P2, ..., Pn} sao cho:
     - P1 đang chờ tài nguyên do P2 giữ
     - P2 đang chờ tài nguyên do P3 giữ
     - ...
     - Pn đang chờ tài nguyên do P1 giữ

## Mô hình hóa Deadlock

### 1. Resource Allocation Graph (RAG)

Resource Allocation Graph là một công cụ đồ họa để mô tả trạng thái cấp phát tài nguyên trong hệ thống. Đồ thị này bao gồm:

- **Đỉnh tiến trình**: Biểu diễn các tiến trình trong hệ thống.
- **Đỉnh tài nguyên**: Biểu diễn các loại tài nguyên.
- **Cạnh yêu cầu**: Từ tiến trình đến tài nguyên, biểu thị tiến trình đang yêu cầu tài nguyên.
- **Cạnh cấp phát**: Từ tài nguyên đến tiến trình, biểu thị tài nguyên đã được cấp phát cho tiến trình.

Nếu đồ thị chứa chu trình và mỗi loại tài nguyên chỉ có một thể hiện (instance), thì hệ thống đang ở trong trạng thái deadlock. Nếu có nhiều thể hiện của một loại tài nguyên, sự hiện diện của chu trình là điều kiện cần nhưng chưa đủ cho deadlock.

### 2. Banker's Algorithm (Thuật toán Banker)

Banker's Algorithm là một thuật toán tránh deadlock, được đề xuất bởi Dijkstra. Thuật toán duy trì thông tin về:

- **Tài nguyên sẵn có (Available)**: Số lượng tài nguyên còn lại của mỗi loại.
- **Phân bổ tối đa (Max)**: Nhu cầu tối đa về tài nguyên của mỗi tiến trình.
- **Phân bổ hiện tại (Allocation)**: Số lượng tài nguyên đã được cấp phát cho mỗi tiến trình.
- **Nhu cầu (Need)**: Số lượng tài nguyên còn cần thiết cho mỗi tiến trình (Max - Allocation).

Thuật toán Banker sử dụng khái niệm "trạng thái an toàn" (safe state) để quyết định có cấp phát tài nguyên cho một yêu cầu hay không. Một trạng thái an toàn là trạng thái mà trong đó có ít nhất một chuỗi tiến trình có thể hoàn thành mà không gây ra deadlock.

## Chiến lược xử lý Deadlock

### 1. Deadlock Prevention (Ngăn chặn Deadlock)

Ngăn chặn deadlock bằng cách loại bỏ ít nhất một trong bốn điều kiện Coffman:

#### a. Loại bỏ Mutual Exclusion
- Khó thực hiện vì nhiều tài nguyên vốn không thể chia sẻ (như máy in).

#### b. Loại bỏ Hold and Wait
- **Phân bổ toàn bộ**: Yêu cầu tiến trình phải yêu cầu tất cả tài nguyên cần thiết trước khi bắt đầu.
- **Phân bổ từng phần**: Tiến trình phải giải phóng tất cả tài nguyên hiện tại trước khi yêu cầu tài nguyên mới.

#### c. Loại bỏ No Preemption
- Cho phép thu hồi tài nguyên khi không thể cấp phát tất cả tài nguyên yêu cầu.
- Tiến trình bị tước quyền sử dụng tài nguyên sẽ được khôi phục khi tất cả tài nguyên cần thiết có sẵn.

#### d. Loại bỏ Circular Wait
- **Cơ chế đánh số toàn cục**: Gán một số nguyên duy nhất cho mỗi loại tài nguyên.
- **Quy tắc yêu cầu**: Tiến trình chỉ có thể yêu cầu tài nguyên theo thứ tự tăng dần của số đó.

### 2. Deadlock Avoidance (Tránh Deadlock)

Tránh deadlock bằng cách không cho hệ thống đi vào trạng thái không an toàn.

#### a. Resource Allocation Graph Algorithm
- Dùng cho trường hợp mỗi loại tài nguyên chỉ có một thể hiện.
- Sử dụng "claim edge" (cạnh yêu cầu) để đánh dấu tiến trình có thể yêu cầu tài nguyên trong tương lai.
- Chỉ cấp phát tài nguyên nếu việc chuyển đổi claim edge thành cạnh cấp phát không tạo ra chu trình.

#### b. Banker's Algorithm
- Dùng cho trường hợp mỗi loại tài nguyên có nhiều thể hiện.
- Chỉ cấp phát tài nguyên nếu hệ thống vẫn ở trạng thái an toàn sau khi cấp phát.

### 3. Deadlock Detection and Recovery (Phát hiện và Khôi phục Deadlock)

Cho phép deadlock xảy ra, nhưng có cơ chế để phát hiện và khôi phục hệ thống.

#### a. Phát hiện Deadlock
- **Đối với một thể hiện của mỗi loại tài nguyên**: Kiểm tra chu trình trong wait-for graph.
- **Đối với nhiều thể hiện của mỗi loại tài nguyên**: Sử dụng thuật toán tương tự Banker's Algorithm.

#### b. Khôi phục từ Deadlock
- **Hủy bỏ tiến trình**: Chấm dứt một hoặc nhiều tiến trình để phá vỡ chu trình deadlock.
  - Hủy bỏ tất cả các tiến trình bị deadlock.
  - Hủy bỏ từng tiến trình cho đến khi chu trình deadlock bị phá vỡ.

- **Đoạt quyền tài nguyên**: Lấy lại tài nguyên từ một hoặc nhiều tiến trình và cấp phát cho tiến trình khác.
  - Cần xem xét: Tiến trình nào sẽ bị tước quyền sử dụng tài nguyên.
  - Tài nguyên nào sẽ bị tước từ tiến trình đó.
  - Tiến trình bị tước quyền có cần trở lại trạng thái nào (rollback).
  - Làm thế nào để tránh starvation (đói tài nguyên).

### 4. Ignore the Problem (Bỏ qua Vấn đề)

Một số hệ điều hành như UNIX và Windows không xử lý deadlock, mà để người dùng tự xử lý hoặc khởi động lại hệ thống khi deadlock xảy ra. Phương pháp này được gọi là "đà đà" (ostrich algorithm).

## So sánh các Chiến lược xử lý Deadlock

| Chiến lược | Ưu điểm | Nhược điểm |
|------------|---------|------------|
| Prevention | - Đảm bảo không có deadlock<br>- Dễ triển khai | - Sử dụng tài nguyên không hiệu quả<br>- Giảm tính đồng thời<br>- Có thể dẫn đến starvation |
| Avoidance | - Sử dụng tài nguyên hiệu quả hơn prevention<br>- Cho phép đồng thời cao hơn | - Yêu cầu biết trước thông tin<br>- Khó triển khai<br>- Overhead xử lý |
| Detection & Recovery | - Không giới hạn việc sử dụng tài nguyên<br>- Cho phép đồng thời cao | - Overhead khi phát hiện<br>- Chi phí khôi phục<br>- Có thể mất dữ liệu khi hủy tiến trình |
| Ignore | - Không có overhead<br>- Đơn giản | - Có thể dẫn đến treo hệ thống<br>- Khó debug |

## Các vấn đề liên quan đến Deadlock

### 1. Livelock

Livelock tương tự như deadlock, nhưng trạng thái của các tiến trình liên tục thay đổi mà không thực sự tiến triển. Ví dụ: hai người gặp nhau trong hành lang hẹp, cả hai cùng dịch sang phải để nhường đường, rồi lại cùng dịch sang trái, cứ như vậy mà không ai đi qua được.

### 2. Resource Starvation (Đói tài nguyên)

Starvation xảy ra khi một tiến trình không bao giờ được cấp phát tài nguyên mà nó cần, mặc dù tài nguyên đó không bị deadlock. Nguyên nhân thường do thuật toán phân phối tài nguyên thiên vị.

### 3. Distributed Deadlock (Deadlock phân tán)

Deadlock trong hệ thống phân tán phức tạp hơn so với trong hệ thống đơn bộ xử lý vì:
- Không có bộ nhớ chung, giao tiếp thông qua truyền thông điệp.
- Không có đồng hồ chung, khó xác định thứ tự sự kiện.
- Khó thu thập thông tin trạng thái toàn cục.

## Kết luận

Deadlock là một vấn đề quan trọng trong hệ điều hành đa nhiệm và cơ sở dữ liệu. Việc hiểu rõ nguyên nhân, điều kiện, và các phương pháp xử lý deadlock là rất quan trọng để thiết kế hệ thống ổn định và hiệu quả. Cách tiếp cận xử lý deadlock phụ thuộc vào môi trường, yêu cầu của hệ thống và sự đánh đổi giữa hiệu suất, độ phức tạp và mức độ bảo đảm an toàn.
# Process in Operating System
**Last Updated : 30 Dec, 2024**

## English Version

### What is a Process?
A process is a program in execution. For example, when we write a program in C or C++ and compile it, the compiler creates binary code. The original code and binary code are both programs. When we actually run the binary code, it becomes a process.

- A process is an 'active' entity instead of a program, which is considered a 'passive' entity.
- A single program can create many processes when run multiple times; for example, when we open a .exe or binary file multiple times, multiple instances begin (multiple processes are created).

### How Does a Process Look Like in Memory?
A process in memory is divided into several distinct sections, each serving a different purpose. Here's how a process typically looks in memory:

1. **Text Section**: Contains executable instructions. It is typically a read-only section.
2. **Stack**: Contains temporary data, such as function parameters, return addresses, and local variables.
3. **Data Section**: Contains global variables.
4. **Heap Section**: Memory dynamically allocated to the process during runtime.

### Attributes of a Process
A process has several important attributes that help the operating system manage and control it. These attributes are stored in a structure called the **Process Control Block (PCB)**. The PCB keeps all the key information about the process, including:

- **Process ID (PID)**: A unique number assigned to each process.
- **Process State**: Shows whether the process is running, waiting, or ready to execute.
- **Priority and CPU Scheduling Information**: Helps decide which process should run next.
- **I/O Information**: Tracks input/output devices the process is using.
- **File Descriptors**: Information about open files and network connections.
- **Accounting Information**: Tracks CPU usage and other resource metrics.
- **Memory Management Information**: Details about the memory space allocated to the process.

### States of a Process
A process is in one of the following states:

1. **New**: Newly created or being created.
2. **Ready**: Ready for execution after creation.
3. **Running**: Currently being executed by the CPU (only one process at a time on a single processor).
4. **Wait (Blocked)**: The process is waiting for I/O access.
5. **Complete (Terminated)**: The process has finished execution.
6. **Suspended Ready**: When the ready queue is full, some processes are moved to this state.
7. **Suspended Blocked**: When the waiting queue is full.

---

## Phiên bản Tiếng Việt

### Tiến trình là gì?
Tiến trình là một chương trình đang được thực thi. Ví dụ, khi viết một chương trình bằng C hoặc C++ và biên dịch nó, trình biên dịch sẽ tạo mã nhị phân. Cả mã nguồn và mã nhị phân đều là chương trình. Khi chúng ta thực sự chạy mã nhị phân, nó trở thành một tiến trình.

- Tiến trình là một thực thể 'động', trong khi chương trình chỉ là một thực thể 'tĩnh'.
- Một chương trình có thể tạo ra nhiều tiến trình khi chạy nhiều lần; ví dụ, khi chúng ta mở một tệp .exe hoặc tệp nhị phân nhiều lần, nhiều phiên bản sẽ bắt đầu (nhiều tiến trình được tạo).

### Cấu trúc của Tiến trình trong Bộ nhớ
Một tiến trình trong bộ nhớ được chia thành nhiều phần riêng biệt, mỗi phần có một chức năng khác nhau. Dưới đây là cách một tiến trình được tổ chức trong bộ nhớ:

1. **Vùng mã (Text Section)**: Chứa các lệnh thực thi, thường là vùng chỉ đọc.
2. **Ngăn xếp (Stack)**: Chứa dữ liệu tạm thời, chẳng hạn như tham số hàm, địa chỉ trả về và biến cục bộ.
3. **Vùng dữ liệu (Data Section)**: Chứa các biến toàn cục.
4. **Vùng heap (Heap Section)**: Phần bộ nhớ được cấp phát động trong thời gian chạy.

### Thuộc tính của Tiến trình
Mỗi tiến trình có một số thuộc tính quan trọng giúp hệ điều hành quản lý và kiểm soát nó. Các thuộc tính này được lưu trữ trong **Bảng điều khiển tiến trình (Process Control Block - PCB)**. PCB giữ tất cả thông tin chính về tiến trình, bao gồm:

- **ID Tiến trình (PID)**: Số nhận dạng duy nhất cho mỗi tiến trình.
- **Trạng thái tiến trình**: Cho biết tiến trình đang chạy, chờ đợi hay sẵn sàng thực thi.
- **Thông tin ưu tiên và lập lịch CPU**: Giúp quyết định tiến trình nào sẽ chạy tiếp theo.
- **Thông tin I/O**: Theo dõi các thiết bị đầu vào/đầu ra mà tiến trình đang sử dụng.
- **Thông tin mô tả tệp (File Descriptors)**: Thông tin về các tệp mở và kết nối mạng.
- **Thông tin tài nguyên (Accounting Information)**: Theo dõi mức độ sử dụng CPU và tài nguyên khác.
- **Thông tin quản lý bộ nhớ**: Chi tiết về vùng nhớ được cấp phát cho tiến trình.

### Trạng thái của Tiến trình
Một tiến trình có thể ở một trong các trạng thái sau:

1. **New (Mới)**: Tiến trình mới được tạo hoặc đang trong quá trình tạo.
2. **Ready (Sẵn sàng)**: Sau khi tạo, tiến trình chuyển sang trạng thái sẵn sàng để thực thi.
3. **Running (Đang chạy)**: Tiến trình hiện đang được CPU thực thi (chỉ một tiến trình có thể chạy tại một thời điểm trên một bộ xử lý đơn).
4. **Wait (Chờ hoặc Bị chặn)**: Khi một tiến trình yêu cầu truy cập I/O.
5. **Complete (Hoàn thành hoặc Kết thúc)**: Tiến trình đã hoàn thành thực thi.
6. **Suspended Ready (Sẵn sàng bị tạm ngưng)**: Khi hàng đợi sẵn sàng đầy, một số tiến trình sẽ chuyển sang trạng thái này.
7. **Suspended Blocked (Bị chặn tạm ngưng)**: Khi hàng đợi chờ đợi đầy.

---

Đây là những khái niệm quan trọng về tiến trình trong hệ điều hành.


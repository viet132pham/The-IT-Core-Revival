# Privileged and Non-Privileged Instructions in Operating System

## English
### Introduction
In an operating system, instructions executed by the CPU are classified into two types: privileged and non-privileged instructions. These classifications help ensure system security and stability by controlling access to critical hardware and kernel-level operations.

### Privileged Instructions
Privileged instructions are commands that can only be executed in kernel mode. These instructions directly interact with system hardware and affect overall system operations. If a user-mode program attempts to execute a privileged instruction, it will result in a trap (exception) and the operating system will handle it appropriately.

#### Examples:
1. **Managing Interrupts:** Enabling or disabling hardware interrupts.
2. **I/O Control:** Directly accessing I/O devices.
3. **Memory Management:** Modifying page tables or handling virtual memory operations.
4. **Process Control:** Changing the mode of execution (switching between user mode and kernel mode).
5. **Shutting Down the System:** Executing commands to power off or restart the computer.

### Non-Privileged Instructions
Non-privileged instructions are those that can be executed in user mode without causing system-wide issues. These instructions do not require direct interaction with hardware and are typically used for regular application tasks.

#### Examples:
1. **Arithmetic Operations:** Addition, subtraction, multiplication, and division.
2. **Logic Operations:** AND, OR, NOT, XOR.
3. **Data Movement:** Loading and storing data in registers and memory.
4. **Control Flow:** Branching, looping, and function calls.
5. **User-Level I/O Operations:** Reading from or writing to files through system calls (without direct hardware access).

### Importance of Privileged Instructions
- Ensures security by preventing unauthorized access to critical system resources.
- Helps maintain system stability by allowing only the operating system to perform certain sensitive operations.
- Prevents malicious programs from compromising system integrity.

---

## Tiếng Việt
### Giới thiệu
Trong hệ điều hành, các lệnh mà CPU thực thi được phân thành hai loại: lệnh đặc quyền (privileged) và lệnh không đặc quyền (non-privileged). Việc phân loại này giúp đảm bảo tính bảo mật và ổn định của hệ thống bằng cách kiểm soát quyền truy cập vào phần cứng quan trọng và các thao tác cấp nhân (kernel-level operations).

### Lệnh Đặc Quyền
Lệnh đặc quyền là các lệnh chỉ có thể được thực thi trong chế độ nhân (kernel mode). Những lệnh này trực tiếp tương tác với phần cứng hệ thống và có thể ảnh hưởng đến toàn bộ hệ thống. Nếu một chương trình chạy ở chế độ người dùng cố gắng thực thi một lệnh đặc quyền, hệ thống sẽ tạo ra một bẫy (trap) và hệ điều hành sẽ xử lý nó một cách thích hợp.

#### Ví dụ:
1. **Quản lý ngắt:** Bật hoặc tắt ngắt phần cứng.
2. **Kiểm soát I/O:** Truy cập trực tiếp vào thiết bị đầu vào/đầu ra.
3. **Quản lý bộ nhớ:** Chỉnh sửa bảng trang hoặc xử lý bộ nhớ ảo.
4. **Kiểm soát tiến trình:** Chuyển đổi chế độ thực thi (chuyển đổi giữa chế độ người dùng và chế độ nhân).
5. **Tắt máy hoặc khởi động lại hệ thống:** Thực hiện các lệnh tắt máy hoặc khởi động lại.

### Lệnh Không Đặc Quyền
Lệnh không đặc quyền là những lệnh có thể được thực thi trong chế độ người dùng mà không gây ảnh hưởng đến toàn bộ hệ thống. Những lệnh này không yêu cầu tương tác trực tiếp với phần cứng và thường được sử dụng cho các tác vụ ứng dụng thông thường.

#### Ví dụ:
1. **Phép toán số học:** Cộng, trừ, nhân, chia.
2. **Phép toán logic:** AND, OR, NOT, XOR.
3. **Di chuyển dữ liệu:** Tải và lưu dữ liệu vào thanh ghi và bộ nhớ.
4. **Điều khiển luồng:** Câu lệnh rẽ nhánh, vòng lặp, và lời gọi hàm.
5. **Thao tác I/O ở cấp độ người dùng:** Đọc/ghi dữ liệu từ tập tin thông qua system call (không truy cập trực tiếp vào phần cứng).

### Tầm Quan Trọng của Lệnh Đặc Quyền
- Đảm bảo an ninh bằng cách ngăn chặn truy cập trái phép vào các tài nguyên hệ thống quan trọng.
- Duy trì tính ổn định của hệ thống bằng cách chỉ cho phép hệ điều hành thực hiện các thao tác nhạy cảm.
- Ngăn chặn các chương trình độc hại làm tổn hại tính toàn vẹn của hệ thống.

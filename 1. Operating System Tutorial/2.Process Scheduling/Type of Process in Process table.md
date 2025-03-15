# Different Types of Processes in Process Table

## English Version

### Last Updated: 23 Jan, 2025

The **process table** is a data structure used by the operating system to keep track of all processes. It is the collection of **Process Control Blocks (PCBs)**, which contain information about each process, such as its **Process ID (PID)**, current state (e.g., running, ready, waiting), CPU usage, memory allocation, and open files.

The process table helps the operating system manage processes efficiently by tracking their progress and resource usage. Each entry in the table corresponds to one process, and the operating system updates it as the process moves through different states in its lifecycle.

### Process States
A process can be in different states such as **new, ready, running, waiting, or terminated**, depending on its activity and resource needs. These states help the operating system manage processes effectively, ensuring smooth execution and optimal resource utilization.

### Types of Processes in Process Table
1. **New (Created) Process**  
   - A process that has been created but is not yet ready for execution. It remains in this state until the operating system assigns the necessary resources.

2. **Ready Process**  
   - A process that is ready to run and is waiting for CPU time. These processes are maintained in a queue called the **ready queue**.

3. **Running Process**  
   - A process currently being executed by the CPU. Only one process (or more in multicore systems) can be in the running state at a time.

4. **Blocked (Waiting) Process**  
   - A process that is waiting for an event to occur, such as I/O completion or resource availability. It cannot proceed until the required condition is met.

5. **Terminated Process**  
   - A process that has completed execution or has been explicitly killed. It remains in the process table briefly before being removed by the OS.

6. **Zombie Process**  
   - A process that has finished execution but remains in the process table because its **parent process has not yet read its exit status**.

7. **Orphan Process**  
   - A child process that is still running while its parent process has terminated. The orphan process continues execution but is no longer monitored by its original parent.

8. **Daemon Process**  
   - A background process that runs independently of user control, usually performing system services. Daemons are typically started at system boot and run continuously until the system shuts down.

---

## Phiên bản Tiếng Việt

### Cập nhật lần cuối: 23/01/2025

**Process Table** (Bảng tiến trình) là một cấu trúc dữ liệu mà hệ điều hành sử dụng để theo dõi tất cả các tiến trình. Nó bao gồm **Process Control Blocks (PCBs)**, chứa các thông tin về từng tiến trình như **Process ID (PID)**, trạng thái hiện tại (ví dụ: running, ready, waiting), mức sử dụng CPU, bộ nhớ và các tệp đang mở.

Process Table giúp hệ điều hành quản lý tiến trình hiệu quả bằng cách theo dõi quá trình hoạt động và việc sử dụng tài nguyên của chúng.

### Trạng thái của tiến trình
Một tiến trình có thể ở các trạng thái như **New, Ready, Running, Waiting, hoặc Terminated**, tùy thuộc vào hoạt động và tài nguyên cần thiết. Những trạng thái này giúp hệ điều hành quản lý tiến trình hiệu quả, đảm bảo thực thi mượt mà và sử dụng tài nguyên tối ưu.

### Các loại tiến trình trong Process Table
1. **New (Tiến trình mới)**  
   - Tiến trình đã được tạo nhưng chưa sẵn sàng để thực thi. Nó ở trạng thái này cho đến khi hệ điều hành cấp phát tài nguyên cần thiết.

2. **Ready (Tiến trình sẵn sàng)**  
   - Tiến trình sẵn sàng chạy và đang chờ CPU cấp quyền thực thi. Các tiến trình này được quản lý trong một **hàng đợi sẵn sàng (ready queue)**.

3. **Running (Tiến trình đang chạy)**  
   - Tiến trình đang được CPU thực thi. Trong một hệ thống đơn lõi, chỉ có một tiến trình có thể ở trạng thái này tại một thời điểm.

4. **Blocked (Tiến trình bị chặn/đang chờ)**  
   - Tiến trình đang chờ một sự kiện xảy ra, chẳng hạn như hoàn tất I/O hoặc tài nguyên khả dụng. Nó không thể tiếp tục cho đến khi điều kiện này được đáp ứng.

5. **Terminated (Tiến trình kết thúc)**  
   - Tiến trình đã hoàn thành thực thi hoặc bị hệ điều hành kết thúc. Nó vẫn còn trong bảng tiến trình một thời gian ngắn trước khi bị loại bỏ.

6. **Zombie Process (Tiến trình Zombie)**  
   - Tiến trình đã kết thúc nhưng vẫn còn trong bảng tiến trình vì **tiến trình cha chưa đọc trạng thái thoát của nó**.

7. **Orphan Process (Tiến trình Mồ Côi)**  
   - Tiến trình con vẫn tiếp tục chạy ngay cả khi tiến trình cha đã kết thúc. Tiến trình mồ côi vẫn hoạt động nhưng không còn được cha giám sát.

8. **Daemon Process (Tiến trình Daemon)**  
   - Tiến trình chạy nền, độc lập với người dùng và thường thực hiện các dịch vụ hệ thống. Daemon thường được khởi động cùng hệ thống và chạy liên tục cho đến khi hệ thống tắt.

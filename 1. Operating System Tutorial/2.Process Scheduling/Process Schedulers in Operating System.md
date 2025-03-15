# Process Schedulers in Operating System (Bộ lập lịch tiến trình trong Hệ điều hành)

**Last Updated: 02 Jan, 2025**

## **1. Introduction (Giới thiệu)**
A process is the instance of a computer program in execution. (Tiến trình là một phiên bản của chương trình máy tính đang thực thi.)

Scheduling is important in operating systems with multiprogramming as multiple processes might be eligible for running at a time. (Lập lịch rất quan trọng trong hệ điều hành đa chương trình vì nhiều tiến trình có thể đủ điều kiện để chạy cùng một lúc.)

One of the key responsibilities of an Operating System (OS) is to decide which programs will execute on the CPU. (Một trong những trách nhiệm chính của Hệ điều hành là quyết định chương trình nào sẽ thực thi trên CPU.)

Process Schedulers are fundamental components of operating systems responsible for deciding the order in which processes are executed by the CPU. (Bộ lập lịch tiến trình là thành phần quan trọng của hệ điều hành, chịu trách nhiệm quyết định thứ tự tiến trình được CPU thực thi.)

---

## **2. What is Process Scheduling? (Lập lịch tiến trình là gì?)**
Process scheduling is the activity of the process manager that handles the removal of the running process from the CPU and the selection of another process based on a particular strategy. (Lập lịch tiến trình là hoạt động của bộ quản lý tiến trình, xử lý việc loại bỏ tiến trình đang chạy khỏi CPU và chọn tiến trình khác dựa trên một chiến lược cụ thể.)

Throughout its lifetime, a process moves between various scheduling queues, such as the ready queue, waiting queue, or devices queue. (Trong suốt vòng đời, một tiến trình di chuyển giữa các hàng đợi lập lịch khác nhau, chẳng hạn như hàng đợi sẵn sàng, hàng đợi chờ hoặc hàng đợi thiết bị.)

---

## **3. Categories of Scheduling (Các loại lập lịch)**
Scheduling falls into one of two categories: (Lập lịch thuộc một trong hai loại sau:)

1. **Non-Preemptive (Không chiếm quyền):** A process’s resource cannot be taken before the process has finished running. (Tài nguyên của một tiến trình không thể bị lấy đi trước khi tiến trình hoàn thành chạy.)
2. **Preemptive (Chiếm quyền):** The OS can switch a process from running state to ready state. (Hệ điều hành có thể chuyển một tiến trình từ trạng thái đang chạy sang trạng thái sẵn sàng.)

---

## **4. Types of Process Schedulers (Các loại Bộ lập lịch tiến trình)**

### **4.1 Long-Term or Job Scheduler (Bộ lập lịch dài hạn)**
- Loads a process from disk to main memory for execution. (Tải tiến trình từ ổ đĩa vào bộ nhớ chính để thực thi.)
- Controls the Degree of Multi-programming. (Kiểm soát mức độ đa chương trình.)
- Maintains a balance between I/O-bound and CPU-bound processes. (Giữ cân bằng giữa tiến trình phụ thuộc vào I/O và tiến trình phụ thuộc vào CPU.)
- Slowest among the three. (Chậm nhất trong ba loại.)

### **4.2 Short-Term or CPU Scheduler (Bộ lập lịch ngắn hạn)**
- Selects one process from the ready state for running. (Chọn một tiến trình từ trạng thái sẵn sàng để chạy.)
- Uses scheduling algorithms to balance CPU allocation. (Sử dụng thuật toán lập lịch để cân bằng phân bổ CPU.)
- Calls dispatcher to execute processes. (Gọi bộ điều phối để thực thi tiến trình.)
- Fastest among the three. (Nhanh nhất trong ba loại.)

### **4.3 Medium-Term Scheduler (Bộ lập lịch trung hạn)**
- Moves processes from memory to disk (swapping). (Di chuyển tiến trình từ bộ nhớ sang ổ đĩa - hoán đổi.)
- Reduces the degree of multiprogramming. (Giảm mức độ đa chương trình.)
- Faster than long-term but slower than short-term scheduler. (Nhanh hơn bộ lập lịch dài hạn nhưng chậm hơn bộ lập lịch ngắn hạn.)

---

## **5. Some Other Schedulers (Một số bộ lập lịch khác)**
- **I/O Schedulers:** Manage execution of I/O operations. (Quản lý thực thi các hoạt động I/O.)
- **Real-Time Schedulers:** Ensure tasks meet deadlines in real-time systems. (Đảm bảo các tác vụ hoàn thành đúng thời hạn trong hệ thống thời gian thực.)

---

## **6. Comparison Among Schedulers (So sánh giữa các bộ lập lịch)**
| Long-Term Scheduler | Short-Term Scheduler | Medium-Term Scheduler |
|---------------------|---------------------|----------------------|
| Job scheduler | CPU scheduler | Process-swapping scheduler |
| Slowest | Fastest | Intermediate speed |
| Controls multi-programming | Less control over multi-programming | Reduces multi-programming |
| Not present in time-sharing | Minimal time-sharing | Used in time-sharing |
| Can re-enter process into memory | Selects ready-to-execute processes | Can re-introduce process into memory |

---

## **7. Context Switching (Chuyển đổi ngữ cảnh)**
Context switching is a mechanism to store and restore the state of a CPU so that process execution can continue later. (Chuyển đổi ngữ cảnh là cơ chế lưu trữ và khôi phục trạng thái CPU để tiếp tục thực thi tiến trình sau đó.)

### **7.1 Steps in Context Switching (Các bước trong chuyển đổi ngữ cảnh)**
1. Saving the state of the current process. (Lưu trạng thái của tiến trình hiện tại.)
2. Loading the state of the new process. (Tải trạng thái của tiến trình mới.)
3. Jumping to the correct location in the program. (Nhảy đến vị trí chính xác trong chương trình.)

---

## **8. Conclusion (Kết luận)**
Process schedulers are essential for managing CPU execution efficiently. (Bộ lập lịch tiến trình rất quan trọng để quản lý hiệu quả việc thực thi CPU.)

By choosing the right process at the right time, schedulers optimize system performance and ensure fair CPU access. (Bằng cách chọn đúng tiến trình vào đúng thời điểm, bộ lập lịch tối ưu hóa hiệu suất hệ thống và đảm bảo truy cập công bằng vào CPU.)

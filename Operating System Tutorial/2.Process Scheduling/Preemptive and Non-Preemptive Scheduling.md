## Preemptive and Non-Preemptive Scheduling

### Last Updated: 03 Feb, 2025

In operating systems, scheduling is the method by which processes are given access to the CPU. Efficient scheduling is essential for optimal system performance and user experience. There are two primary types of CPU scheduling: preemptive and non-preemptive.

Understanding the differences between preemptive and non-preemptive scheduling helps in designing and choosing the right scheduling algorithms for various types of operating systems.

### Preemptive Scheduling
The operating system can interrupt or preempt a running process to allocate CPU time to another process, typically based on priority or time-sharing policies. Mainly a process is switched from the running state to the ready state. Algorithms based on preemptive scheduling include:
- Round Robin (RR)
- Shortest Remaining Time First (SRTF)
- Priority Scheduling (Preemptive version)

#### Advantages of Preemptive Scheduling
- Prevents monopolization of the processor, making the system more reliable.
- Improves the average response time.
- Efficient for multi-programming environments.
- Used in modern operating systems like Windows, Linux, and macOS.

#### Disadvantages of Preemptive Scheduling
- More complex to implement in operating systems.
- Context switching causes overhead and takes extra time.
- Might cause starvation: a low-priority process may be continuously preempted by higher-priority processes.
- Concurrency problems may arise when accessing shared memory.

### Non-Preemptive Scheduling
In non-preemptive scheduling, a running process cannot be interrupted by the operating system; it voluntarily relinquishes control of the CPU. Once allocated, the process holds the CPU until it terminates or enters a waiting state.

Algorithms based on non-preemptive scheduling include:
- First Come, First Serve (FCFS)
- Shortest Job First (SJF, primarily non-preemptive)
- Priority Scheduling (Non-preemptive version)

#### Advantages of Non-Preemptive Scheduling
- Simpler to implement in an operating system.
- Minimal scheduling overhead.
- Uses fewer computational resources.

#### Disadvantages of Non-Preemptive Scheduling
- Vulnerable to denial-of-service attacks if a process monopolizes the CPU.
- Higher average response time since no round-robin scheduling is available.

### Differences Between Preemptive and Non-Preemptive Scheduling
| Parameter | Preemptive Scheduling | Non-Preemptive Scheduling |
|-----------|----------------------|--------------------------|
| Basic | CPU is allocated for a limited time. | CPU is allocated until process completes or enters waiting state. |
| Interrupt | Process can be interrupted. | Process cannot be interrupted. |
| Starvation | Low-priority processes may starve. | Long processes may delay shorter ones. |
| Overhead | High due to context switching. | Low due to fewer context switches. |
| Flexibility | More flexible. | More rigid. |
| Cost | Higher due to scheduling complexity. | Lower. |
| Response Time | Lower response time. | Higher response time. |
| Decision Making | Done by the scheduler based on priority and time slice. | Done by the process itself. |
| Process Control | OS has greater control over scheduling. | OS has less control over scheduling. |
| Concurrency Overhead | Higher due to frequent interruptions. | Lower as processes are not preempted. |
| Examples | Round Robin, Shortest Remaining Time First. | First Come, First Serve, Shortest Job First. |

Choosing between preemptive and non-preemptive scheduling depends on system requirements, process priorities, and the need for fairness versus efficiency.

**Preemptive and Non-Preemptive Scheduling**  
**Lịch quản CPU tiên quyền và không tiên quyền**  

### Preemptive Scheduling (Lịch quản CPU tiên quyền)
Preemptive Scheduling là phương pháp lịch quản trong đó hệ điều hành có thể tạm dừng (preempt) một tiến trình đang chạy để nhường CPU cho tiến trình khác, thường dựa trên độ ưu tiên hoặc chính sách chia sẻ thời gian.

- **Ví dụ**: Round Robin (RR), Shortest Remaining Time First (SRTF), Priority Scheduling (phiên bản tiên quyền).
- **Ưu điểm**:
  - Ngăn chặn tiến trình chiếm đoạt CPU vô thời hạn.
  - Tăng tốc độ đáp ứng.
  - Hữu ích trong hệ thống đa chương trình.
  - Được sử dụng trong hầu hết các hệ điều hành hiện đại (Windows, Linux, macOS).
- **Nhược điểm**:
  - Cài đặt phức tạp.
  - Thời gian xử lý lớn do việc tạm dừng và chuyển bối cảnh (context switch).
  - D  - D\u1eexy ra hiện tượng “starvation” (tiến trình độ ưu tiên thấp bị đẫm chân).
  - Vấn đề đồng thời khi nhiều tiến trình truy cập bộ nhớ chia sẻ.

---

### Non-Preemptive Scheduling (Lịch quản CPU không tiên quyền)
Non-Preemptive Scheduling là phương pháp trong đó tiến trình được cấp CPU sẽ giữ nó cho đến khi hoàn thành hoặc tự chuyển sang trạng thái chờ.

- **Ví dụ**: First Come First Serve (FCFS), Shortest Job First (SJF - phiên bản không tiên quyền), Priority Scheduling (phiên bản không tiên quyền).
- **Ưu điểm**:
  - Dễ triển khai, tính toán đơn giản.
  - Tiết kiệm tài nguyên xử lý.
  - Thích hợp cho các hệ thống đơn giản (Windows 3.11, macOS cổ).
- **Nhược điểm**:
  - Có thể dẫn đến "denial of service" (một tiến trình độc hại chiếm CPU vô hạn).
  - Thời gian đáp ứng cao hơn.
  - Tình linh hoạt thấp.

---

### So sánh Preemptive và Non-Preemptive Scheduling
| **Tiêu chí** | **Preemptive Scheduling** | **Non-Preemptive Scheduling** |
|----------------|------------------------|----------------------------|
| **Cách hoạt động** | CPU có thể bị thu hồi bất kỳ lúc nào | CPU do tiến trình chiếm dụng đến khi hoàn thành |
| **Ngắt quá trình** | Có thể bị gián đoạn | Chỉ kết thúc khi tiến trình hoàn thành |
| **Starvation** | Dễ bị do các tiến trình độ ưu tiên cao | Dễ bị do tiến trình có burst time lâu |
| **Chi phí** | Cao hơn do chi phí chuyển bối cảnh | Thấp hơn |
| **Thời gian đáp ứng** | Nhanh hơn | Chậm hơn |
| **Điều khiển** | Hệ điều hành quyết định | Tiến trình tự quyết định |
| **Ví dụ** | Round Robin, SRTF | FCFS, SJF |

---

Tóm lại, Preemptive Scheduling linh hoạt và hiệu quả hơn nhưng cát giảm tài nguyên, trong khi Non-Preemptive Scheduling đơn giản nhưng có thể dẫn đến các vấn đề starvation hoặc "denial of service."


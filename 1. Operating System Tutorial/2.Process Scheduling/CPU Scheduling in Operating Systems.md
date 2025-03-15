# CPU Scheduling in Operating Systems

## Last Updated: 14 Jan, 2025

## English Version

### Introduction
CPU scheduling is a process used by the operating system to decide which task or process gets to use the CPU at a particular time. This is important because a CPU can only handle one task at a time, but there are usually many tasks that need to be processed. The following are different purposes of CPU scheduling:

- Maximize CPU utilization.
- Minimize response and waiting time of the process.

### Need for a CPU Scheduling Algorithm
CPU scheduling ensures that whenever the CPU remains idle, the OS has at least selected one of the available processes in the ready queue. In multiprogramming, if the long-term scheduler selects multiple I/O binding processes, then most of the time, the CPU remains idle. An effective scheduling algorithm improves resource utilization.

### Terminologies Used in CPU Scheduling
- **Arrival Time**: The time at which the process arrives in the ready queue.
- **Completion Time**: The time at which the process completes its execution.
- **Burst Time**: Time required by a process for CPU execution.
- **Turnaround Time**: Time difference between completion time and arrival time.
  - \( Turnaround Time = Completion Time - Arrival Time \)
- **Waiting Time (W.T)**: Time difference between turnaround time and burst time.
  - \( Waiting Time = Turnaround Time - Burst Time \)

### Factors to Consider When Designing a CPU Scheduling Algorithm
- **CPU Utilization**: The goal is to keep the CPU as busy as possible (ranges from 40% to 90%).
- **Throughput**: Number of processes completed per unit of time.
- **Turnaround Time**: Total time taken for a process from arrival to completion.
- **Waiting Time**: Time spent by a process in the ready queue.
- **Response Time**: Time taken from submission to the first response.

### Types of CPU Scheduling
- **Preemptive Scheduling**: Process can be interrupted and moved to a ready state before completion.
- **Non-Preemptive Scheduling**: A process runs until completion or voluntarily moves to a waiting state.

### CPU Scheduling Algorithms
1. **FCFS – First Come, First Serve**
2. **SJF – Shortest Job First**
3. **SRTF – Shortest Remaining Time First**
4. **Round Robin**
5. **Priority Scheduling**
6. **HRRN – Highest Response Ratio Next**
7. **Multiple Queue Scheduling**
8. **Multilevel Feedback Queue Scheduling**

---

## Phiên bản Tiếng Việt

### Giới thiệu
Lập lịch CPU là quá trình được hệ điều hành sử dụng để quyết định tác vụ hoặc tiến trình nào được sử dụng CPU vào một thời điểm cụ thể. Điều này quan trọng vì CPU chỉ có thể xử lý một tác vụ tại một thời điểm, nhưng thường có nhiều tác vụ cần được xử lý. Mục đích chính của lập lịch CPU bao gồm:

- Tối đa hóa việc sử dụng CPU.
- Giảm thiểu thời gian phản hồi và thời gian chờ của tiến trình.

### Tại sao cần thuật toán lập lịch CPU?
Lập lịch CPU đảm bảo rằng bất cứ khi nào CPU nhàn rỗi, hệ điều hành đã chọn ít nhất một trong số các tiến trình có sẵn trong hàng đợi sẵn sàng. Trong hệ thống đa chương trình, nếu bộ lập lịch dài hạn chọn quá nhiều tiến trình ràng buộc I/O, CPU có thể bị nhàn rỗi. Một thuật toán lập lịch hiệu quả sẽ cải thiện việc sử dụng tài nguyên.

### Thuật ngữ trong lập lịch CPU
- **Thời gian đến (Arrival Time)**: Thời điểm tiến trình đến hàng đợi sẵn sàng.
- **Thời gian hoàn thành (Completion Time)**: Thời điểm tiến trình hoàn thành thực thi.
- **Thời gian CPU (Burst Time)**: Thời gian cần thiết để tiến trình thực thi trên CPU.
- **Thời gian quay vòng (Turnaround Time)**: Hiệu giữa thời gian hoàn thành và thời gian đến.
  - \( Turnaround Time = Completion Time - Arrival Time \)
- **Thời gian chờ (Waiting Time - W.T)**: Hiệu giữa thời gian quay vòng và thời gian CPU.
  - \( Waiting Time = Turnaround Time - Burst Time \)

### Các yếu tố cần xem xét khi thiết kế thuật toán lập lịch CPU
- **Sử dụng CPU**: Mục tiêu là giữ CPU hoạt động càng nhiều càng tốt (thường từ 40% đến 90%).
- **Thông lượng (Throughput)**: Số lượng tiến trình hoàn thành mỗi đơn vị thời gian.
- **Thời gian quay vòng**: Tổng thời gian từ khi tiến trình đến đến khi hoàn thành.
- **Thời gian chờ**: Thời gian tiến trình đợi trong hàng đợi sẵn sàng.
- **Thời gian phản hồi**: Thời gian từ khi tiến trình được gửi đến khi nó tạo ra phản hồi đầu tiên.

### Các loại lập lịch CPU
- **Lập lịch có thu hồi (Preemptive Scheduling)**: Tiến trình có thể bị dừng giữa chừng và chuyển sang trạng thái sẵn sàng trước khi hoàn thành.
- **Lập lịch không thu hồi (Non-Preemptive Scheduling)**: Tiến trình sẽ chạy cho đến khi hoàn thành hoặc tự chuyển sang trạng thái chờ.

### Các thuật toán lập lịch CPU
1. **FCFS – First Come, First Serve (Đến trước, phục vụ trước)**
2. **SJF – Shortest Job First (Việc ngắn nhất làm trước)**
3. **SRTF – Shortest Remaining Time First (Thời gian còn lại ngắn nhất làm trước)**
4. **Round Robin (Lập lịch vòng tròn)**
5. **Priority Scheduling (Lập lịch theo mức ưu tiên)**
6. **HRRN – Highest Response Ratio Next (Tỷ lệ phản hồi cao nhất kế tiếp)**
7. **Multiple Queue Scheduling (Lập lịch hàng đợi đa cấp)**
8. **Multilevel Feedback Queue Scheduling (Lập lịch hàng đợi phản hồi đa cấp)**

# Process Management - Quản lý Quy trình

## Introduction - Giới thiệu
Process management for a single-tasking or batch-processing system is simple because only one process runs at a time. However, with multiple processes (multiprogramming or multitasking) running simultaneously, process management becomes complex because the CPU needs to be utilized efficiently by many processes. Multiple active processes may share resources like memory and communicate with each other. This makes things more complicated as the Operating System (OS) must ensure process synchronization.

Quản lý quy trình trong hệ thống xử lý đơn nhiệm hoặc xử lý hàng loạt rất dễ dàng vì chỉ có một quy trình hoạt động tại một thời điểm. Với nhiều quy trình (đa chương trình hoặc đa nhiệm) đang hoạt động, việc quản lý quy trình trở nên phức tạp vì CPU cần được nhiều quy trình sử dụng hiệu quả. Nhiều quy trình đang hoạt động có thể chia sẻ tài nguyên như bộ nhớ và có thể giao tiếp với nhau. Điều này càng làm cho mọi thứ trở nên phức tạp hơn vì Hệ điều hành phải thực hiện đồng bộ hóa quy trình.

The main advantage of multiprogramming is system responsiveness and better CPU utilization. We can run multiple processes in an interleaved manner on a single CPU. For example, when the current process is busy with I/O, we allocate the CPU to another process.

Xin hãy nhớ rằng lợi thế chính của việc lập trình đa chương trình là khả năng phản hồi của hệ thống và sử dụng CPU tốt hơn. Chúng ta có thể chạy nhiều quy trình theo cách xen kẽ trên một CPU duy nhất. Ví dụ, khi quy trình hiện tại đang bận rộn với IO, chúng ta sẽ gán CPU cho một số quy trình khác.

---

## CPU-bound vs. I/O-bound Processes - Quy trình liên kết CPU so với quy trình liên kết I/O
A CPU-bound process requires more CPU time and spends most of its time in the running state. An I/O-bound process requires more I/O time and less CPU time. An I/O-bound process spends more time in the waiting state.

Một tiến trình bị ràng buộc bởi CPU cần nhiều thời gian CPU hơn hoặc dành nhiều thời gian hơn ở trạng thái đang chạy. Một tiến trình bị ràng buộc bởi I/O cần nhiều thời gian I/O hơn và ít thời gian CPU hơn. Một tiến trình bị ràng buộc bởi I/O dành nhiều thời gian hơn ở trạng thái chờ.

---

## Process Scheduling - Lập lịch Quy trình
Process scheduling is an essential part of an OS that manages processes. It refers to the mechanism used by the OS to determine which process runs next. The goal of process scheduling is to enhance overall system performance by maximizing CPU utilization, minimizing turnaround time, and improving system responsiveness.

Lập kế hoạch quy trình là một phần không thể thiếu của hệ điều hành quản lý quy trình. Nó đề cập đến cơ chế được hệ điều hành sử dụng để xác định quy trình nào sẽ chạy tiếp theo. Mục tiêu của lập lịch quy trình là cải thiện hiệu suất hệ thống tổng thể bằng cách tối đa hóa việc sử dụng CPU, giảm thiểu thời gian thông lượng và cải thiện thời gian phản hồi của hệ thống.

---

## Tasks of Process Management - Nhiệm vụ Quản lý Quy trình
Process management is crucial in multitasking or multiprogramming operating systems. It involves:

### 1. Process Creation and Termination - Tạo và Chấm dứt Quy trình
Creating a process involves generating a process ID, setting up a Process Control Block (PCB), etc. A process can be terminated by the OS or its parent process. Termination involves deallocating all resources assigned to the process.

Việc tạo quy trình bao gồm việc tạo ID quy trình, thiết lập Khối điều khiển quy trình, v.v. Một quy trình có thể bị chấm dứt bởi hệ điều hành hoặc bởi quy trình cha. Việc chấm dứt quy trình bao gồm việc xóa tất cả các tài nguyên được phân bổ cho quy trình đó.

### 2. CPU Scheduling - Lên lịch CPU
In a multiprogramming system, many processes require CPU time. The OS ensures smooth and efficient execution of multiple processes.

Trong hệ thống đa chương trình, nhiều tiến trình cần có CPU. Nhiệm vụ của Hệ điều hành là đảm bảo thực hiện trơn tru và hiệu quả nhiều tiến trình.

### 3. Deadlock Handling - Xử lý Bế tắc
Ensuring the system does not enter a state where two or more processes cannot proceed due to circular dependencies.

Đảm bảo hệ thống không rơi vào trạng thái mà hai hoặc nhiều tiến trình không thể tiếp tục hoạt động do phụ thuộc lẫn nhau theo chu kỳ.

### 4. Interprocess Communication (IPC) - Giao tiếp giữa các tiến trình
The OS provides mechanisms like shared memory and message passing for cooperating processes to communicate with each other.

Hệ điều hành cung cấp các tiện ích như bộ nhớ chia sẻ và truyền tin nhắn để các tiến trình hợp tác giao tiếp với nhau.

### 5. Process Synchronization - Đồng bộ hóa Quy trình
Synchronization ensures that multiple processes access shared resources (such as memory) in a controlled and predictable manner.

Đồng bộ hóa quy trình là sự phối hợp thực hiện của nhiều quy trình trong một hệ thống đa chương trình để đảm bảo rằng chúng truy cập vào các tài nguyên được chia sẻ (như bộ nhớ) theo cách được kiểm soát và có thể dự đoán được.

---

## Process Scheduling Algorithms - Thuật toán Lập lịch Quy trình
Different scheduling algorithms are used in an OS to determine process execution order:

1. **First-Come, First-Served (FCFS)**: Processes are executed in the order they arrive. No priority is given.
2. **Shortest Job First (SJF)**: The process with the shortest burst time is executed first to minimize average waiting time.
3. **Round Robin (RR)**: Each process gets a fixed time slice. If unfinished, it moves to the end of the queue.
4. **Priority Scheduling**: Processes are assigned priority levels; the highest priority process is executed first.
5. **Multilevel Queue Scheduling**: Processes are divided into different priority queues, each using a specific scheduling algorithm.

Hệ điều hành có thể sử dụng các thuật toán lập lịch khác nhau để lập lịch các tiến trình: FCFS, SJF, RR, Lập lịch ưu tiên, Hàng đợi đa cấp.

---

## Conclusion - Kết luận
Process management is a vital OS function that ensures multiple programs run smoothly and efficiently. It involves process creation, scheduling, termination, resource management, and IPC. Effective process management optimizes system performance, stability, and responsiveness.

Tóm lại, quản lý quy trình là một chức năng quan trọng của hệ điều hành, đảm bảo nhiều chương trình có thể chạy trơn tru và hiệu quả. Nó bao gồm việc tạo, lập lịch và kết thúc các quy trình, cũng như quản lý tài nguyên và xử lý giao tiếp giữa các quy trình.

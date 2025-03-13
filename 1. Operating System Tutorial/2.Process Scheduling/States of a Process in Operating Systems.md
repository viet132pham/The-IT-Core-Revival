# States of a Process in Operating Systems (Trạng thái của một tiến trình trong Hệ điều hành)

## Introduction (Giới thiệu)
In an operating system, a process is a program that is being executed. A process goes through different states during its lifecycle. Understanding these states helps in managing processes efficiently.  
Trong hệ điều hành, một tiến trình là một chương trình đang được thực thi. Tiến trình trải qua nhiều trạng thái khác nhau trong vòng đời của nó. Hiểu các trạng thái này giúp quản lý tiến trình hiệu quả.

## Two-State Model (Mô hình hai trạng thái)
The simplest model of a process lifecycle consists of two states:
1. **Running**: The process is actively using the CPU.
2. **Not Running**: The process is not currently using the CPU and is waiting.

Mô hình đơn giản nhất về vòng đời tiến trình gồm hai trạng thái:
1. **Đang chạy (Running)**: Tiến trình đang sử dụng CPU.
2. **Không chạy (Not Running)**: Tiến trình không sử dụng CPU và đang chờ.

## Five-State Model (Mô hình năm trạng thái)
To better manage processes, the operating system divides the lifecycle into five states:
1. **New**: Process is created but not yet running.
2. **Ready**: Process is waiting to be executed.
3. **Running**: Process is currently using the CPU.
4. **Blocked/Waiting**: Process is waiting for an event (e.g., I/O operation).
5. **Terminated**: Process has finished execution or was stopped.

Để quản lý tiến trình tốt hơn, hệ điều hành chia vòng đời tiến trình thành năm trạng thái:
1. **Mới (New)**: Tiến trình được tạo nhưng chưa chạy.
2. **Sẵn sàng (Ready)**: Tiến trình đang chờ để được thực thi.
3. **Đang chạy (Running)**: Tiến trình đang sử dụng CPU.
4. **Bị chặn/Đang chờ (Blocked/Waiting)**: Tiến trình đang chờ một sự kiện (ví dụ: thao tác nhập/xuất).
5. **Kết thúc (Terminated)**: Tiến trình đã hoàn thành hoặc bị dừng.

## Seven-State Model (Mô hình bảy trạng thái)
Some systems further refine the states to include:
1. **New**
2. **Ready**
3. **Running**
4. **Blocked/Waiting**
5. **Terminated**
6. **Suspend Ready**: Process is swapped out of memory but can return.
7. **Suspend Blocked**: Blocked process is swapped out.

Một số hệ thống bổ sung các trạng thái:
1. **Mới (New)**
2. **Sẵn sàng (Ready)**
3. **Đang chạy (Running)**
4. **Bị chặn/Đang chờ (Blocked/Waiting)**
5. **Kết thúc (Terminated)**
6. **Sẵn sàng bị treo (Suspend Ready)**: Tiến trình bị đưa ra khỏi bộ nhớ nhưng có thể quay lại.
7. **Bị treo khi chặn (Suspend Blocked)**: Tiến trình bị chặn và bị đưa ra khỏi bộ nhớ.

## Process Transitions (Chuyển đổi trạng thái tiến trình)
A process can move between states based on execution and resource availability:
- **New → Ready**: Process created and ready to execute.
- **Ready → Running**: Process gets CPU time.
- **Running → Blocked**: Waiting for an event.
- **Blocked → Ready**: Event occurs, process ready again.
- **Running → Terminated**: Process completes execution.
- **Running → Ready**: CPU time expired, another process runs.

Tiến trình có thể di chuyển giữa các trạng thái:
- **Mới → Sẵn sàng**: Tiến trình được tạo và sẵn sàng thực thi.
- **Sẵn sàng → Đang chạy**: Tiến trình được cấp CPU.
- **Đang chạy → Bị chặn**: Chờ một sự kiện.
- **Bị chặn → Sẵn sàng**: Sự kiện hoàn thành, tiến trình sẵn sàng.
- **Đang chạy → Kết thúc**: Tiến trình hoàn thành.
- **Đang chạy → Sẵn sàng**: Hết thời gian CPU, tiến trình khác chạy.

## Conclusion (Kết luận)
Understanding process states helps in optimizing resource management and improving system efficiency. These states define how an operating system schedules and manages processes.

Hiểu các trạng thái của tiến trình giúp tối ưu hóa quản lý tài nguyên và cải thiện hiệu suất hệ thống. Những trạng thái này xác định cách hệ điều hành lập lịch và quản lý tiến trình.

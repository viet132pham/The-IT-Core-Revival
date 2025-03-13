## Process Creation and Deletions in Operating Systems

### Process Creation
A process is an instance of a program running, and its lifecycle includes various stages such as creation, execution, and deletion. The operating system handles process creation by allocating necessary resources and assigning each process a unique identifier.

#### Steps of Process Creation:
1. The operating system assigns a unique Process Identifier (PID) to the new process.
2. It allocates required memory space for the process, including the program, data, and stack.
3. It initializes the Process Control Block (PCB), which contains:
   - Process ID and Parent Process ID.
   - Processor register values (stack pointer, program counter, etc.).
   - Process state (initially 'New').
   - Priority and scheduling information.
4. The process state transitions from 'New' to 'Ready', and the operating system schedules it for execution.

#### Process Creation in UNIX:
- **fork()**: Creates a new child process that is a copy of the parent.
- **exec()**: Replaces the child’s memory with a new program.
- **waitpid()**: Makes the parent wait until the child finishes.

Example:
```c
int pid = fork();
if (pid == 0)
{     
   /* Child process  */     
   exec("foo");
}
else
{     
   /* Parent process */     
   waitpid(pid, &status, options);
}
```

#### Process Creation in Windows:
- **CreateProcess()**: Creates a new process with its own memory space and initializes it.
- Unlike UNIX, Windows does not use a direct copy of the parent process.

---

### Process Deletion
Process termination involves releasing resources once a process completes execution.

#### Ways a Process Can Be Terminated:
1. **Normal Termination**: The process completes execution and calls **exit()**.
2. **Abnormal Termination**: An error forces the process to call **abort()**.
3. **Termination by Parent**: The parent terminates a child using **kill()**.
4. **Termination by Signal**: Signals like **SIGKILL** forcefully terminate a process.

#### Cascaded Termination:
- If a parent process exits, all its child processes are also terminated.

---

## Tạo và Xóa Tiến Trình trong Hệ Điều Hành

### Tạo Tiến Trình
Một tiến trình là một phiên bản đang chạy của một chương trình. Hệ điều hành quản lý việc tạo tiến trình bằng cách cấp phát tài nguyên và gán một định danh duy nhất.

#### Các bước tạo tiến trình:
1. Hệ điều hành gán một **PID (Process Identifier)** duy nhất.
2. Cấp phát bộ nhớ cho chương trình, dữ liệu và ngăn xếp.
3. Khởi tạo **Process Control Block (PCB)** chứa:
   - PID và PID của tiến trình cha.
   - Giá trị thanh ghi (stack pointer, program counter, v.v.).
   - Trạng thái tiến trình (ban đầu là 'New').
   - Thông tin ưu tiên và lập lịch.
4. Tiến trình chuyển trạng thái từ **'New' sang 'Ready'**, sẵn sàng để được thực thi.

#### Tạo Tiến Trình trong UNIX:
- **fork()**: Tạo một tiến trình con từ tiến trình cha.
- **exec()**: Thay thế bộ nhớ tiến trình con bằng chương trình mới.
- **waitpid()**: Khiến tiến trình cha đợi tiến trình con hoàn thành.

Ví dụ:
```c
int pid = fork();
if (pid == 0)
{     
   /* Tiến trình con */     
   exec("foo");
}
else
{     
   /* Tiến trình cha */     
   waitpid(pid, &status, options);
}
```

#### Tạo Tiến Trình trong Windows:
- **CreateProcess()**: Tạo tiến trình mới với không gian bộ nhớ riêng biệt.
- Windows không sao chép tiến trình cha như UNIX.

---

### Xóa Tiến Trình
Hệ điều hành giải phóng tài nguyên sau khi một tiến trình kết thúc.

#### Các cách một tiến trình có thể bị xóa:
1. **Xóa bình thường**: Tiến trình hoàn tất và gọi **exit()**.
2. **Xóa bất thường**: Một lỗi khiến tiến trình gọi **abort()**.
3. **Xóa bởi tiến trình cha**: Tiến trình cha dùng **kill()** để xóa tiến trình con.
4. **Xóa bởi tín hiệu**: Các tín hiệu như **SIGKILL** có thể buộc tiến trình dừng ngay lập tức.

#### Xóa theo chuỗi:
- Nếu một tiến trình cha kết thúc, tất cả tiến trình con của nó cũng bị xóa theo.

---

### Tổng kết
- Tiến trình được tạo bằng **fork()** (UNIX) hoặc **CreateProcess()** (Windows).
- Việc xóa tiến trình có thể diễn ra do hoàn thành nhiệm vụ, lỗi hoặc tín hiệu từ hệ điều hành.


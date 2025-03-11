# Introduction of System Call

## English Version
### What is a System Call?
A **system call** is a mechanism used by programs to request services from the operating system's kernel. It provides an interface between user applications and the OS, allowing access to hardware resources such as files, memory, and devices.

### Purpose of System Calls
System calls are essential for:
- **Process Management**: Creating, executing, and terminating processes.
- **File Management**: Creating, reading, writing, and closing files.
- **Device Management**: Communicating with hardware devices like printers and storage.
- **Memory Management**: Allocating and freeing memory.
- **Networking**: Establishing and managing network connections.

### Types of System Calls
1. **Process Control**: `fork()`, `exec()`, `exit()`, `wait()`
2. **File Management**: `open()`, `read()`, `write()`, `close()`
3. **Device Management**: `ioctl()`, `read()`, `write()`
4. **Information Maintenance**: `getpid()`, `alarm()`, `sleep()`
5. **Communication**: `pipe()`, `shmget()`, `mmap()`, `socket()`

### Example of System Call in C
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main() {
    int pid = fork();
    if (pid == 0) {
        // Child process
        execlp("ls", "ls", NULL);
    } else {
        // Parent process
        wait(NULL);
        printf("Child process finished execution\n");
    }
    return 0;
}
```

---

## Phiên bản Tiếng Việt
### Hệ thống gọi (System Call) là gì?
**System Call** là cơ chế cho phép các chương trình yêu cầu dịch vụ từ kernel của hệ điều hành. Nó cung cấp giao diện giữa ứng dụng người dùng và hệ điều hành, cho phép truy cập vào tài nguyên phần cứng như tệp tin, bộ nhớ và thiết bị.

### Mục đích của System Call
System Call được sử dụng để:
- **Quản lý tiến trình**: Tạo, thực thi và kết thúc tiến trình.
- **Quản lý tệp tin**: Tạo, đọc, ghi, đóng tệp tin.
- **Quản lý thiết bị**: Giao tiếp với các thiết bị phần cứng như máy in và ổ cứng.
- **Quản lý bộ nhớ**: Cấp phát và giải phóng bộ nhớ.
- **Mạng**: Thiết lập và quản lý kết nối mạng.

### Các loại System Call
1. **Điều khiển tiến trình**: `fork()`, `exec()`, `exit()`, `wait()`
2. **Quản lý tệp tin**: `open()`, `read()`, `write()`, `close()`
3. **Quản lý thiết bị**: `ioctl()`, `read()`, `write()`
4. **Bảo trì thông tin**: `getpid()`, `alarm()`, `sleep()`
5. **Giao tiếp**: `pipe()`, `shmget()`, `mmap()`, `socket()`

### Ví dụ về System Call trong C
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main() {
    int pid = fork();
    if (pid == 0) {
        // Tiến trình con
        execlp("ls", "ls", NULL);
    } else {
        // Tiến trình cha
        wait(NULL);
        printf("Tiến trình con đã hoàn thành\n");
    }
    return 0;
}

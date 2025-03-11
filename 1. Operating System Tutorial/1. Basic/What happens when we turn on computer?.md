# Computer Boot Process | Quá trình khởi động máy tính

## English Version

### 1. Power On and Electricity Supply
- When you press the power button, the **Power Supply Unit (PSU)** provides electricity to all components, including the **CPU, RAM, Hard Drive, and Motherboard**.
- The PSU checks voltage stability before fully supplying power.

**Example:**
- If the voltage is unstable, the PSU prevents power supply to protect components, and the computer will not turn on.

---

### 2. BIOS/UEFI Initialization
- **BIOS (Basic Input Output System) or UEFI (Unified Extensible Firmware Interface)** stored in ROM is activated.
- **Tasks:**
  - Checks hardware (CPU, RAM, keyboard, mouse, etc.) via **POST (Power-On Self-Test)**.
  - If there is a hardware error, it beeps to indicate the issue.
  - Searches for and loads the OS from a boot device.

**Example:**
- If the RAM is faulty or not properly connected, you will hear **beeping sounds** from the BIOS, signaling RAM issues.
- UEFI provides a graphical interface, making hardware settings adjustments easier than traditional BIOS.

---

### 3. Bootloader Loads the Operating System
- After BIOS/UEFI finishes testing, it searches for the **bootloader** on the hard drive.
- The bootloader is a small program that loads the OS into RAM.
- Examples:
  - **Windows** uses **Windows Boot Manager (BOOTMGR)**.
  - **Linux** uses **GRUB (Grand Unified Bootloader)**.

**Example:**
- If the hard drive has no OS or is corrupted, you will see the message **"No bootable device found"**.
- On **dual-boot systems (Windows + Linux)**, GRUB allows you to choose the OS.

---

### 4. OS Loads into RAM
- The bootloader finds the **kernel** of the OS and loads it into **RAM**.
- The kernel is the most critical part of the OS, managing system resources.
- After loading the kernel, the OS starts its core services and processes.

**Example:**
- If your PC boots slowly, it might be due to an **old HDD (instead of an SSD)** or **too many startup applications**.
- In Windows, you can check startup programs via **Task Manager → Startup**.

---

### 5. User Login and GUI Load
- The OS initializes essential services like **network management, device drivers**.
- The login screen appears, allowing the user to enter credentials.
- After login, the OS loads the Graphical User Interface (GUI) or terminal (for Linux servers).

**Example:**
- If you enter the wrong password multiple times, the system might lock your account or require additional verification (Windows Hello, fingerprint, etc.).
- If there is a driver issue, the screen might flicker or have incorrect resolution settings.

---

### Summary Table

| **Step**  | **Description** | **Common Errors** |
|----------|----------------|------------------|
| 1️⃣ Power On | PSU supplies power to components | Computer doesn't turn on |
| 2️⃣ BIOS/UEFI | Checks hardware via POST | RAM error → beeping sounds |
| 3️⃣ Bootloader | Finds and loads the OS | "No bootable device found" |
| 4️⃣ OS Loads | Kernel and system processes start | Slow boot due to HDD |
| 5️⃣ Login | User enters credentials | Incorrect password, driver issues |

📌 **Conclusion:**
Every time you turn on a computer, a complex sequence of events happens within seconds to bring you to the login screen. Any issue in this process can prevent the computer from booting up properly. 💻🚀

---

## Phiên bản Tiếng Việt

### 1. Bật máy và cung cấp điện
- Khi bạn nhấn nút nguồn, **Bộ nguồn PSU (Power Supply Unit)** cung cấp điện cho toàn bộ linh kiện như **CPU, RAM, Ổ cứng, Bo mạch chủ**.
- PSU kiểm tra điện áp trước khi cấp điện toàn bộ.

**Ví dụ:**
- Nếu điện áp không ổn định, PSU sẽ không cấp điện, làm máy không bật được.

---

### 2. BIOS/UEFI khởi động
- **BIOS (Basic Input Output System) hoặc UEFI (Unified Extensible Firmware Interface)** trong ROM được kích hoạt.
- **Nhiệm vụ:**
  - Kiểm tra phần cứng (CPU, RAM, bàn phím, chuột, v.v.) bằng **POST (Power-On Self-Test)**.
  - Nếu có lỗi, BIOS sẽ pát tiếng "bíp".
  - Tìm và nạp hệ điều hành.

**Ví dụ:**
- RAM hỏng sẽ gây ra **tiếng bíp** là cảnh báo.
- UEFI hỗ trợ giao diện đồ họa, giúp cài đặt dễ hơn so với BIOS truyền thống.

---

### 3. Bootloader tìm và tải hệ điều hành
- Bootloader là một chương trình nhỏ giúp nạp hệ điều hành vào RAM.

**Ví dụ:**
- "No bootable device found" xảy ra khi ổ cứng không có hĐH hoặc bị hỏng.

---

(Tiếp tục tương tự với các bước còn lại)

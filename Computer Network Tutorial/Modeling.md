# OSI Model Data Flow and Protocols

## 1. OSI Model Data Flow

### Data Transmission Through OSI Layers

```
Application Layer       → HTTP, HTTPS, FTP, SMTP
Presentation Layer      → SSL/TLS, JPEG, MPEG, GIF
Session Layer           → NetBIOS, PPTP, RPC
Transport Layer         → TCP, UDP
Network Layer           → IP, ICMP, ARP, OSPF, RIP, BGP
Data Link Layer         → Ethernet, Wi-Fi (802.11), MAC Addressing
Physical Layer          → Bits transmitted via cable, fiber optics, or radio waves
```

### Responsibilities of Each Layer

| OSI Layer | Data Unit | Responsibility |
|-----------|-----------|----------------|
| Application Layer | Raw Data | Interface with user applications |
| Presentation Layer | Encoded Data | Data formatting, encryption, compression |
| Session Layer | Session Data | Session control and synchronization |
| Transport Layer | Segments | Reliable/unreliable transmission |
| Network Layer | Packets | Logical addressing and routing |
| Data Link Layer | Frames | Physical addressing and MAC processing |
| Physical Layer | Bits | Signal transmission over media |

### Example: Web Browsing over HTTPS

1. **Application Layer**: Browser sends HTTP/HTTPS request to the web server.
2. **Presentation Layer**: TLS encrypts the request before transmission.
3. **Session Layer**: Session is established between client and server.
4. **Transport Layer**: TCP segments data for reliable transmission.
5. **Network Layer**: IP packets are routed to the server.
6. **Data Link Layer**: Ethernet/Wi-Fi encapsulates packets into frames.
7. **Physical Layer**: Frames are converted into electrical signals or wireless transmission.

---

## 2. OSI Model Protocols in Detail

### Application Layer Protocols
- **HTTP/HTTPS**: Web browsing and secure data transmission.
- **FTP**: File transfers between client and server.
- **SMTP**: Email transmission protocol.

### Presentation Layer Protocols
- **SSL/TLS**: Encrypts web communication.
- **JPEG/MPEG**: Media encoding formats.

### Session Layer Protocols
- **NetBIOS**: Name resolution in Windows networks.
- **PPTP**: VPN tunneling protocol.
- **RPC**: Remote execution of procedures.

### Transport Layer Protocols
- **TCP**: Reliable, connection-oriented data transmission.
- **UDP**: Fast, connectionless communication.

### Network Layer Protocols
- **IP**: Logical addressing and packet forwarding.
- **ICMP**: Network diagnostics (ping, traceroute).
- **ARP**: Resolves IP addresses to MAC addresses.
- **OSPF/RIP/BGP**: Routing protocols for path determination.

### Data Link Layer Protocols
- **Ethernet**: Standard for wired network communication.
- **Wi-Fi (802.11)**: Wireless network communication.

### Physical Layer Transmission
- **Cable (Ethernet, Fiber Optic)**: Wired data transfer.
- **Radio Waves (Wi-Fi, Bluetooth)**: Wireless communication.

---

This document provides a detailed overview of how data flows through the OSI model and describes the role of each layer along with the associated protocols. Each section illustrates how protocols work in real-world scenarios, ensuring a complete understanding of network communication.


# Mô hình OSI và cách dữ liệu truyền qua các tầng

## 1. Tổng quan về mô hình OSI
Mô hình OSI (Open Systems Interconnection) là một mô hình mạng chuẩn chia thành 7 tầng, giúp hiểu rõ cách dữ liệu truyền qua hệ thống mạng.

## 2. Cách dữ liệu truyền qua các tầng
Dữ liệu đi từ ứng dụng (người dùng) xuống tầng vật lý khi gửi và ngược lại khi nhận:

1. **Tầng Ứng dụng (Application Layer)** → Dữ liệu (Data)
2. **Tầng Trình diễn (Presentation Layer)** → Dữ liệu (Data)
3. **Tầng Phiên (Session Layer)** → Dữ liệu (Data)
4. **Tầng Giao vận (Transport Layer)** → Phân đoạn (Segment)
5. **Tầng Mạng (Network Layer)** → Gói tin (Packet)
6. **Tầng Liên kết dữ liệu (Data Link Layer)** → Khung (Frame)
7. **Tầng Vật lý (Physical Layer)** → Bit

---

## 3. Nhiệm vụ của từng tầng và giao thức sử dụng

### **7. Tầng Ứng dụng (Application Layer)**
- **Nhiệm vụ**: Cung cấp giao diện cho người dùng và ứng dụng để sử dụng mạng.
- **Giao thức**: HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, Telnet, SSH

### **6. Tầng Trình diễn (Presentation Layer)**
- **Nhiệm vụ**: Chuyển đổi định dạng dữ liệu, mã hóa và nén dữ liệu.
- **Giao thức**: SSL/TLS, JPEG, GIF, MPEG, ASCII, Unicode

### **5. Tầng Phiên (Session Layer)**
- **Nhiệm vụ**: Thiết lập, duy trì và kết thúc phiên kết nối giữa hai thiết bị.
- **Giao thức**: NetBIOS, PPTP, RPC

### **4. Tầng Giao vận (Transport Layer)**
- **Nhiệm vụ**: Chia nhỏ dữ liệu, đảm bảo truyền tải đáng tin cậy hoặc không đáng tin cậy.
- **Giao thức**: TCP, UDP, SCTP, DCCP
- **Định dạng dữ liệu**: **Segment**

### **3. Tầng Mạng (Network Layer)**
- **Nhiệm vụ**: Định tuyến dữ liệu giữa các thiết bị, sử dụng địa chỉ IP.
- **Giao thức**: IP, ICMP, ARP, RIP, OSPF, BGP, MPLS
- **Định dạng dữ liệu**: **Packet**

### **2. Tầng Liên kết dữ liệu (Data Link Layer)**
- **Nhiệm vụ**: Chuyển đổi dữ liệu thành các khung và kiểm soát lỗi.
- **Giao thức**: Ethernet, Wi-Fi, PPP, MAC
- **Định dạng dữ liệu**: **Frame**

### **1. Tầng Vật lý (Physical Layer)**
- **Nhiệm vụ**: Truyền dữ liệu dưới dạng tín hiệu điện, sóng vô tuyến, hoặc ánh sáng.
- **Giao thức**: USB, Bluetooth, IEEE 802.11 (Wi-Fi), Fiber Optic
- **Định dạng dữ liệu**: **Bit**

---

## 4. Mô hình trực quan về dữ liệu khi truyền qua các tầng

Ví dụ khi một trang web được gửi từ máy chủ đến máy khách:

1. **Application Layer**: HTTP request → "GET /index.html"
2. **Presentation Layer**: Mã hóa dữ liệu bằng TLS
3. **Session Layer**: Thiết lập kết nối phiên
4. **Transport Layer**: TCP chia dữ liệu thành **segments**
5. **Network Layer**: Thêm địa chỉ IP vào mỗi segment, tạo thành **packets**
6. **Data Link Layer**: Đóng gói packets thành **frames** và gửi qua mạng
7. **Physical Layer**: Chuyển đổi thành các **bits** và gửi qua cáp hoặc sóng vô tuyến

Ngược lại, khi dữ liệu đến máy nhận, nó được xử lý theo trình tự ngược lại từ tầng 1 lên tầng 7.

---

## 5. Kết luận
- Mô hình OSI giúp hiểu rõ cách dữ liệu được truyền tải và xử lý trong mạng.
- Mỗi tầng có vai trò riêng, đảm bảo việc truyền dữ liệu chính xác và hiệu quả.
- Hiểu cách các giao thức hoạt động ở mỗi tầng giúp ta thiết kế, quản trị và xử lý sự cố mạng tốt hơn.



# Mô hình OSI - Quá trình truyền dữ liệu giữa các tầng

## 1️⃣ Quá trình truyền dữ liệu qua các tầng OSI

### 📌 Ví dụ thực tế
💡 **Bạn gửi tin nhắn "Hello" qua TCP/IP đến một máy tính khác**.

#### **Tầng 7-5 (Application - Presentation - Session):**
- Ứng dụng tạo dữ liệu: `"Hello"`.
- Dữ liệu có thể được nén, mã hóa hoặc chuyển đổi định dạng trước khi truyền đi.

#### **Tầng 4 (Transport - TCP/UDP):**
- Dữ liệu `"Hello"` được chia thành **TCP Segment** hoặc **UDP Datagram**.
- Thêm **TCP Header** hoặc **UDP Header**, chứa thông tin về **cổng nguồn, cổng đích, số thứ tự gói tin**.

```plaintext
TCP Segment: [TCP Header] + "Hello"
```

#### **Tầng 3 (Network - IP):**
- **TCP Segment** được đóng vào **IP Packet**.
- Thêm **IP Header**, chứa **địa chỉ IP nguồn và đích**.

```plaintext
IP Packet: [IP Header] + [TCP Segment]
```

#### **Tầng 2 (Data Link - Ethernet, Wi-Fi):**
- **IP Packet** được đóng vào **Ethernet Frame** hoặc **Wi-Fi Frame**.
- Thêm **MAC Header**, chứa **địa chỉ MAC nguồn và đích**.

```plaintext
Ethernet Frame: [MAC Header] + [IP Packet]
```

#### **Tầng 1 (Physical - Bit):**
- **Frame** được chuyển thành **tín hiệu điện, sóng vô tuyến hoặc xung quang học**.
- Truyền qua cáp mạng, Wi-Fi hoặc cáp quang đến thiết bị đích.

---

## 2️⃣ Sơ đồ minh họa quá trình đóng gói dữ liệu
```plaintext
[Data]      ↓  [TCP Header] + [Data]  → TCP Segment      ↓  [IP Header] + [TCP Segment]  → IP Packet      ↓  [MAC Header] + [IP Packet]  → Ethernet Frame      ↓  010101010101 (Tín hiệu vật lý truyền đi)
```
🔥 **Dữ liệu di chuyển từ Application Layer xuống Physical Layer, được đóng gói dần dần trước khi truyền đi!** 🚀

---

## 3️⃣ Giao thức hoạt động ở mỗi tầng

| **Tầng OSI**       | **Giao thức phổ biến**                                      |
|--------------------|-----------------------------------------------------------|
| **Application (7)** | HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS                  |
| **Presentation (6)** | SSL/TLS, JPEG, GIF, MPEG, ASCII, Unicode                 |
| **Session (5)**     | NetBIOS, PPTP, RPC, SOCKS                                |
| **Transport (4)**   | TCP, UDP, SCTP, QUIC                                     |
| **Network (3)**     | IP, ICMP, ARP, RIP, OSPF, BGP                             |
| **Data Link (2)**   | Ethernet, Wi-Fi (802.11), PPP, MAC, ARP                   |
| **Physical (1)**    | Ethernet (cáp đồng), Fiber Optic, Wi-Fi, Bluetooth       |

🔎 **Mỗi tầng có vai trò riêng, đảm bảo dữ liệu được truyền đi chính xác và hiệu quả giữa các thiết bị trong mạng!** 💡

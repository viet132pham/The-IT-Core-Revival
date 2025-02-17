# 🏛 Mô Hình OSI (OSI Model)

## 🔹 Tổng Quan
- **Mô hình OSI (Open Systems Interconnection)** là một khung lý thuyết chia giao tiếp mạng thành **7 tầng** để dễ hiểu và chuẩn hóa.
- Giúp các hệ thống khác nhau có thể giao tiếp với nhau thông qua các giao thức mạng.

---

## 🌍 **7 Tầng của Mô Hình OSI**

### 1️⃣ **Tầng 7 - Ứng Dụng (Application Layer)**
- **Vai trò:** Cung cấp giao diện trực tiếp cho ứng dụng người dùng giao tiếp với mạng.
- **Giao thức:** HTTP, FTP, SMTP, POP3, IMAP, DNS...
- **Ví dụ:** Khi bạn mở trình duyệt và nhập URL, trình duyệt gửi yêu cầu HTTP đến server.

---

### 2️⃣ **Tầng 6 - Trình Bày (Presentation Layer)**
- **Vai trò:** Chuyển đổi định dạng dữ liệu giữa ứng dụng và mạng.
- **Chức năng chính:** Mã hóa, nén dữ liệu.
- **Ví dụ:** SSL/TLS mã hóa dữ liệu để truyền an toàn.

---

### 3️⃣ **Tầng 5 - Phiên (Session Layer)**
- **Vai trò:** Quản lý phiên kết nối giữa hai thiết bị.
- **Chức năng chính:** Mở, duy trì, đóng phiên giao tiếp.
- **Ví dụ:** Khi bạn đăng nhập vào một website, tầng này duy trì phiên làm việc.

---

### 4️⃣ **Tầng 4 - Giao Vận (Transport Layer)**
- **Vai trò:** Đảm bảo dữ liệu được gửi toàn vẹn và theo đúng thứ tự.
- **Giao thức:** TCP (đảm bảo tin cậy), UDP (không đảm bảo tin cậy, nhanh hơn).
- **Ví dụ:** Khi tải file qua HTTP, TCP đảm bảo file được tải đầy đủ và không bị lỗi.

---

### 5️⃣ **Tầng 3 - Mạng (Network Layer)**
- **Vai trò:** Định tuyến gói tin đến đích thông qua các địa chỉ IP.
- **Giao thức:** IP, ICMP, ARP, RIP, OSPF, BGP.
- **Thiết bị:** Router.
- **Ví dụ:** Khi bạn truy cập website, dữ liệu được định tuyến qua nhiều router để đến đúng server.

---

### 6️⃣ **Tầng 2 - Liên Kết Dữ Liệu (Data Link Layer)**
- **Vai trò:** Kiểm soát truy cập và đảm bảo dữ liệu không bị lỗi khi truyền qua mạng vật lý.
- **Giao thức:** Ethernet, PPP, Wi-Fi (802.11), MAC.
- **Thiết bị:** Switch, Bridge.
- **Ví dụ:** Card mạng (NIC) của bạn sử dụng địa chỉ MAC để gửi dữ liệu đến đúng thiết bị trong mạng LAN.

---

### 7️⃣ **Tầng 1 - Vật Lý (Physical Layer)**
- **Vai trò:** Truyền dữ liệu dưới dạng tín hiệu điện, sóng radio hoặc ánh sáng.
- **Thiết bị:** Cáp mạng, hub, repeater, modem.
- **Ví dụ:** Khi bạn cắm dây Ethernet vào máy tính, dữ liệu được truyền đi dưới dạng tín hiệu điện.

---

## 🏆 **Tóm Tắt Mô Hình OSI**
| Tầng | Tên | Chức năng chính | Giao thức / Thiết bị |
|------|----------------|----------------------|--------------------------|
| 7️⃣ | Ứng dụng | Giao diện ứng dụng | HTTP, FTP, SMTP, DNS |
| 6️⃣ | Trình bày | Mã hóa, chuyển đổi định dạng | SSL/TLS, JPEG, MP3 |
| 5️⃣ | Phiên | Quản lý phiên kết nối | NetBIOS, RPC |
| 4️⃣ | Giao vận | Truyền dữ liệu tin cậy | TCP, UDP |
| 3️⃣ | Mạng | Định tuyến gói tin | IP, ICMP, OSPF, BGP, Router |
| 2️⃣ | Liên kết dữ liệu | Kiểm soát truy cập mạng | Ethernet, MAC, Switch |
| 1️⃣ | Vật lý | Truyền tín hiệu vật lý | Cáp mạng, Wi-Fi, Hub |

---

## 📌 **Mẹo Nhớ 7 Tầng OSI**
- **Từ dưới lên:** *Please Do Not Throw Sausage Pizza Away* (Physical, Data Link, Network, Transport, Session, Presentation, Application).
- **Từ trên xuống:** *All People Seem To Need Data Processing* (Application, Presentation, Session, Transport, Network, Data Link, Physical).

---

## 🎯 **Tại Sao Cần Hiểu Mô Hình OSI?**
✅ Giúp xác định vị trí lỗi mạng và tối ưu hóa hệ thống.
✅ Hiểu cách các thiết bị mạng giao tiếp.
✅ Chuẩn bị cho phỏng vấn về mạng và System Design.

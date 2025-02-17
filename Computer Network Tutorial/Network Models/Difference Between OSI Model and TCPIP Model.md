# OSI vs. TCP/IP Model Comparison

## 🌍 OSI Model
- **Definition:** The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes network communication.
- **Structure:** It has **7 layers** arranged vertically.
- **Use Case:** Mainly used as a reference model for teaching and designing networks.
- **Layers:**
  1. Physical (Bits, cables, and hardware transmission)
  2. Data Link (MAC addresses, frames, switches)
  3. Network (IP addresses, routers, packet forwarding)
  4. Transport (TCP, UDP, segmentation, flow control)
  5. Session (Establishes, maintains, and ends communication)
  6. Presentation (Data formatting, encryption, compression)
  7. Application (User interaction, HTTP, FTP, email)

## 🌐 TCP/IP Model
- **Definition:** The TCP/IP model is a practical framework used in real-world networking, especially for the Internet.
- **Structure:** It has **4 layers** arranged horizontally.
- **Use Case:** Defines standard protocols for internet communication.
- **Layers:**
  1. Network Interface (Similar to OSI's Physical & Data Link layers)
  2. Internet (Similar to OSI's Network layer, includes IP routing)
  3. Transport (Includes TCP, UDP, similar to OSI's Transport layer)
  4. Application (Merges OSI's Session, Presentation, and Application layers)

## 📊 Key Differences
| Feature          | OSI Model (Vertical) | TCP/IP Model (Horizontal) |
|----------------|------------------|-------------------|
| **Layers** | 7 | 4 |
| **Design** | Theoretical | Practical |
| **Usage** | Used as a reference model | Used in real-world networking |
| **Development** | Developed by ISO | Developed by DARPA (US Department of Defense) |
| **Protocol Dependency** | Independent of specific protocols | Tightly integrated with TCP/IP suite |
| **Application Support** | Explicit separation of services | Merges multiple functionalities |

---

# So sánh mô hình OSI và TCP/IP

## 🌍 Mô hình OSI
- **Định nghĩa:** OSI (Open Systems Interconnection) là mô hình khái niệm chuẩn hóa giao tiếp mạng.
- **Cấu trúc:** Gồm **7 tầng**, sắp xếp theo chiều dọc.
- **Ứng dụng:** Chủ yếu dùng làm mô hình tham chiếu để giảng dạy và thiết kế mạng.
- **Các tầng:**
  1. Vật lý (Bit, cáp, truyền dữ liệu qua phần cứng)
  2. Liên kết dữ liệu (Địa chỉ MAC, khung dữ liệu, switch)
  3. Mạng (Địa chỉ IP, bộ định tuyến, chuyển tiếp gói tin)
  4. Giao vận (TCP, UDP, điều khiển luồng dữ liệu)
  5. Phiên (Thiết lập, duy trì và kết thúc kết nối)
  6. Trình bày (Định dạng dữ liệu, mã hóa, nén dữ liệu)
  7. Ứng dụng (Giao tiếp người dùng, HTTP, FTP, email)

## 🌐 Mô hình TCP/IP
- **Định nghĩa:** Mô hình TCP/IP là khung giao tiếp thực tế được sử dụng phổ biến trong mạng Internet.
- **Cấu trúc:** Gồm **4 tầng**, sắp xếp theo chiều ngang.
- **Ứng dụng:** Định nghĩa các giao thức tiêu chuẩn cho truyền thông Internet.
- **Các tầng:**
  1. Giao diện mạng (Tương tự tầng Vật lý & Liên kết dữ liệu của OSI)
  2. Internet (Tương tự tầng Mạng của OSI, xử lý định tuyến IP)
  3. Giao vận (Gồm TCP, UDP, tương tự tầng Giao vận của OSI)
  4. Ứng dụng (Gộp các chức năng của tầng Phiên, Trình bày và Ứng dụng của OSI)

## 📊 Sự khác biệt chính
| Đặc điểm          | Mô hình OSI (Dọc) | Mô hình TCP/IP (Ngang) |
|----------------|------------------|-------------------|
| **Số tầng** | 7 | 4 |
| **Thiết kế** | Lý thuyết | Thực tế |
| **Ứng dụng** | Là mô hình tham chiếu | Được sử dụng trong mạng thực tế |
| **Phát triển** | Được phát triển bởi ISO | Được phát triển bởi DARPA (Bộ Quốc phòng Mỹ) |
| **Phụ thuộc giao thức** | Độc lập với giao thức cụ thể | Gắn chặt với bộ giao thức TCP/IP |
| **Hỗ trợ ứng dụng** | Tách biệt rõ ràng các dịch vụ | Gộp nhiều chức năng |

# Data Link Layer in OSI Model

## English

### Overview
The Data Link Layer (DLL) is the second layer in the OSI model, responsible for node-to-node data transfer. It ensures error-free data transmission between adjacent network nodes and manages access to the physical transmission medium.

### Functions of Data Link Layer
- **Framing**: Divides data into manageable frames for transmission.
- **Error Detection and Correction**: Detects and corrects errors that occur during data transmission.
- **Flow Control**: Ensures that the sender does not overwhelm the receiver with data.
- **Access Control**: Determines which device has control over the communication channel at a given time.

---

### Switching Techniques
Switching techniques determine how data is transmitted within a network. The primary types include:
- **Circuit Switching**: Establishes a dedicated path between source and destination.
- **Packet Switching**: Divides data into packets and sends them individually.
- **Message Switching**: Entire messages are sent from node to node without dividing them into packets.

---

### Virtual LAN (VLAN)
VLAN is a technique that logically divides a physical network into multiple independent networks. It enhances network security and efficiency by isolating broadcast domains without needing additional hardware.

---

### Link Aggregation
Link aggregation combines multiple network connections into a single logical link to increase bandwidth and provide redundancy.

---

### Framing
Framing is the process of encapsulating data with headers and footers to define its boundaries. Common framing methods include:
- **Character Count**: Uses a header specifying frame length.
- **Byte Stuffing**: Adds special characters to indicate frame boundaries.
- **Bit Stuffing**: Inserts extra bits to prevent confusion with frame delimiters.

---

### Error Detection & Correction
- **Error Detection**: Identifies corrupted data using techniques like Parity Check, Checksum, and Cyclic Redundancy Check (CRC).
- **Error Correction**: Fixes detected errors using methods like Hamming Code.

---

### Flow Control
Flow control mechanisms regulate data transmission rates to prevent buffer overflow at the receiver. Common techniques:
- **Stop and Wait ARQ**: The sender waits for an acknowledgment before sending the next frame.
- **Sliding Window Protocol**:
  - **Go-Back-N**: Resends all frames after an error.
  - **Selective Repeat**: Resends only the erroneous frames.

---

### Piggybacking
Piggybacking improves efficiency by allowing acknowledgment packets to carry additional data instead of sending separate control frames.

---

### Data Link Layer Protocols
Common protocols operating at the Data Link Layer:
- **Ethernet (IEEE 802.3)**: Used in wired LANs.
- **Wi-Fi (IEEE 802.11)**: Wireless networking standard.
- **PPP (Point-to-Point Protocol)**: Used in direct connections.
- **HDLC (High-Level Data Link Control)**: Synchronous data link layer protocol.

---

## Tiếng Việt

### Tổng quan
Tầng Liên kết Dữ liệu (Data Link Layer - DLL) là tầng thứ hai trong mô hình OSI, chịu trách nhiệm truyền dữ liệu từ nút này đến nút khác trong mạng. Nó đảm bảo dữ liệu được truyền không có lỗi và quản lý quyền truy cập vào phương tiện truyền dẫn.

### Chức năng của Tầng Liên kết Dữ liệu
- **Đóng gói dữ liệu (Framing)**: Chia dữ liệu thành các khung để truyền tải.
- **Phát hiện và sửa lỗi (Error Detection and Correction)**: Xác định và sửa lỗi dữ liệu.
- **Điều khiển luồng dữ liệu (Flow Control)**: Đảm bảo tốc độ truyền tải phù hợp.
- **Kiểm soát truy cập (Access Control)**: Xác định thiết bị nào có quyền truy cập vào đường truyền.

---

### Kỹ thuật chuyển mạch (Switching Techniques)
Các kỹ thuật chuyển mạch phổ biến:
- **Chuyển mạch kênh (Circuit Switching)**: Thiết lập đường truyền cố định giữa hai thiết bị.
    - 📌 Khái niệm:
        - Một đường truyền vật lý chuyên biệt được thiết lập trước khi truyền dữ liệu.
    Toàn bộ băng thông được dành riêng cho kết nối trong suốt thời gian truyền.
    - 📌 Đặc điểm:
        - ✔ Dữ liệu truyền theo thứ tự, không bị trễ.
        - ✔ Đảm bảo băng thông cố định, phù hợp với truyền thoại, video.
        - ✖ Không hiệu quả vì đường truyền vẫn chiếm dụng ngay cả khi không có dữ liệu.
    - 📌 Ví dụ:
        - 📞 Cuộc gọi điện thoại truyền thống: Khi bạn gọi điện, một kênh liên lạc riêng được thiết lập giữa hai bên và duy trì đến khi cuộc gọi kết thúc.
        
- **Chuyển mạch gói (Packet Switching)**: Chia dữ liệu thành các gói nhỏ để truyền độc lập.
    - 📌 Khái niệm:
        - Dữ liệu được chia nhỏ thành các gói tin (packets) và truyền độc lập qua mạng.
        - Không có đường truyền cố định, mỗi gói có thể đi theo các tuyến đường khác nhau.
    - 📌 Đặc điểm:
        - ✔ Sử dụng hiệu quả tài nguyên mạng, tiết kiệm băng thông.
        - ✔ Khả năng tự động định tuyến khi có sự cố.
        - ✖ Có thể xảy ra độ trễ, mất gói tin.
    - 📌 Các phương pháp:
        - 🔹 Datagram Packet Switching: Mỗi gói tin có địa chỉ riêng, có thể đi các tuyến khác nhau.
        - 🔹 Virtual Circuit Switching: Tạo một kênh ảo tạm thời trước khi truyền toàn bộ dữ liệu.
    - 📌 Ví dụ:
        - 🌐 Internet: Khi bạn gửi email hoặc duyệt web, dữ liệu được chia thành các gói tin và truyền qua nhiều tuyến khác nhau trước khi đến đích.
- **Chuyển mạch thông điệp (Message Switching)**: Gửi toàn bộ thông điệp từ nút này sang nút khác mà không chia thành gói.
    - 📌 Khái niệm:
        - Toàn bộ thông điệp được truyền từ nút này sang nút khác theo kiểu "store-and-forward" (lưu trữ và chuyển tiếp).
    - 📌 Đặc điểm:
        - ✔ Không cần thiết lập kênh cố định như chuyển mạch mạch.
        - ✔ Giảm mất dữ liệu vì thông điệp được lưu trữ trước khi chuyển tiếp.
        - ✖ Gây trễ lớn do phải lưu trữ và chờ trước khi truyền tiếp.
    - 📌 Ví dụ:
        - 📠 Dịch vụ chuyển fax hoặc tin nhắn văn bản (trước khi có Internet).

---

### Mạng LAN ảo (Virtual LAN - VLAN)
- VLAN là công nghệ chia mạng vật lý thành nhiều mạng độc lập, giúp nâng cao bảo mật và hiệu suất mạng mà không cần thêm phần cứng.
    - 🔹 VLAN là gì?
        - VLAN (Mạng LAN ảo) là một công nghệ mạng cho phép chia một mạng vật lý thành nhiều mạng logic (ảo), giúp quản lý và tối ưu hóa lưu lượng mạng hiệu quả hơn.
    - 📌 Tại sao cần VLAN?
        - Cải thiện hiệu suất: Giảm tắc nghẽn bằng cách chia nhỏ broadcast domain.
        - Bảo mật tốt hơn: Ngăn cách các nhóm thiết bị, hạn chế truy cập trái phép.
        - Quản lý linh hoạt: Dễ dàng cấu hình, di chuyển và thay đổi mà không cần thay đổi phần cứng.
    - 🔹 Cách hoạt động của VLAN
        - Trong một mạng LAN thông thường, tất cả các thiết bị kết nối với một switch đều thuộc cùng một mạng (broadcast domain).
        - Khi sử dụng VLAN, switch có thể phân chia thành nhiều mạng ảo, mỗi mạng hoạt động như một LAN độc lập.
        - Chỉ các thiết bị trong cùng VLAN mới có thể giao tiếp trực tiếp với nhau, nếu khác VLAN thì cần router hoặc thiết bị Layer 3 để kết nối.
    - 📌 Ví dụ thực tế:
        - 🎓 Một trường đại học có thể chia mạng thành các VLAN:
        - VLAN 10: Khoa Công nghệ thông tin
        - VLAN 20: Phòng Quản lý sinh viên
        - VLAN 30: Ký túc xá
        - => Nhờ VLAN, dữ liệu của từng nhóm không bị lẫn lộn, tăng hiệu suất và bảo mật.
    - 🔹 Giao tiếp giữa các VLAN
        - Vì VLAN chia mạng thành các subnet khác nhau, các thiết bị trong VLAN khác nhau không thể giao tiếp trực tiếp. Để kết nối giữa VLAN, ta cần:
            - Router (Router-on-a-stick): Sử dụng một cổng router để chuyển đổi giữa các VLAN.
            - Layer 3 Switch: Switch có chức năng định tuyến giữa các VLAN.

- "Virtual LAN (VLAN) is a concept in which we can divide the devices logically on layer 2 (data link layer). Generally, layer 3 devices divide the broadcast domain but the broadcast domain can be divided by switches using the concept of VLAN. 
A broadcast domain is a network segment in which if a device broadcast a packet then all the devices in the same broadcast domain will receive it. The devices in the same broadcast domain will receive all the broadcast packets but it is limited to switches only as routers don’t forward out the broadcast packet. To forward out the packets to different VLAN (from one VLAN to another) or broadcast domains, inter Vlan routing is needed. Through VLAN, different small-size sub-networks are created which are comparatively easy to handle. " Giai thich doan tren:
=> doạn này nói về cách VLAN chia nhỏ broadcast domain và cách giao tiếp giữa các VLAN. 
- Để hiểu rõ hơn, mình sẽ giải thích từng phần:
    - 1️⃣ Layer 2 (Data Link Layer) và VLAN
    Thông thường, switch hoạt động ở Layer 2 và không chia broadcast domain.
    Nhưng VLAN giúp chia nhỏ broadcast domain bằng cách gán thiết bị vào các nhóm logic khác nhau, dù chúng vẫn được kết nối cùng một switch.
    - 2️⃣ Broadcast Domain là gì?
    Broadcast Domain là phạm vi mà trong đó, nếu một thiết bị gửi gói tin broadcast (gói tin đến tất cả thiết bị), thì tất cả các thiết bị trong cùng broadcast domain sẽ nhận được.
    Mặc định, switch không chia nhỏ broadcast domain, nên nếu có 100 máy trong cùng switch, thì khi một máy gửi broadcast, 99 máy còn lại đều nhận được (gây tắc nghẽn).
    - 3️⃣ VLAN giúp gì ở đây?
    VLAN giúp chia nhỏ một switch thành nhiều mạng LAN ảo (mỗi VLAN là một broadcast domain riêng biệt).
        - Ví dụ:
            - VLAN 10: Nhóm nhân sự (HR)
            - VLAN 20: Nhóm IT
            - VLAN 30: Nhóm tài chính
            - => Các máy trong VLAN chỉ nhận broadcast trong VLAN đó, không bị ảnh hưởng bởi các VLAN khác.
    - 4️⃣ Tại sao cần Inter-VLAN Routing?
    Vì mỗi VLAN là một broadcast domain riêng, nên các máy thuộc VLAN khác nhau không thể giao tiếp trực tiếp.
    Switch Layer 2 không thể chuyển tiếp gói tin giữa các VLAN, vì nó chỉ biết xử lý MAC address.
    Để các VLAN có thể giao tiếp, ta cần một thiết bị hoạt động ở Layer 3 (router hoặc Layer 3 switch) để thực hiện Inter-VLAN Routing.

- 📌 Ví dụ thực tế:
    - Nếu một máy trong VLAN 10 (Nhân sự) muốn gửi dữ liệu đến máy trong VLAN 20 (IT), nó cần gửi qua router hoặc switch Layer 3 để định tuyến giữa các VLAN.

- 💡 Tóm gọn:
    - VLAN chia nhỏ broadcast domain ngay trên switch mà không cần router.
    - Các thiết bị trong cùng VLAN có thể giao tiếp bình thường.
    - Nếu muốn gửi dữ liệu giữa VLAN khác nhau, cần router hoặc switch Layer 3 để định tuyến gói tin (Inter-VLAN Routing).


---

### Gộp liên kết (Link Aggregation)
Gộp liên kết kết hợp nhiều kết nối mạng thành một liên kết logic để tăng băng thông và cung cấp dự phòng.

---

### Đóng gói dữ liệu (Framing)

🔹 Frame trong Data Link Layer (DLL) là gì?
Trong Tầng Liên Kết Dữ Liệu (Data Link Layer - DLL) của mô hình OSI, dữ liệu được chia thành các đơn vị nhỏ gọi là frame. Frame là đơn vị dữ liệu cơ bản mà tầng này sử dụng để truyền thông tin qua mạng vật lý.

🔹 Cấu trúc của một Frame
Một frame điển hình bao gồm các thành phần chính sau:

- Header (Tiêu đề)
    - Địa chỉ MAC nguồn
    - Địa chỉ MAC đích
    - Loại hoặc độ dài của frame
- Payload (Dữ liệu)
    - Chứa dữ liệu từ tầng trên (thường là từ Network Layer).
- Trailer (Phần kết thúc)
    - CRC (Cyclic Redundancy Check): Kiểm tra lỗi để đảm bảo tính toàn vẹn dữ liệu.

Các loại Frame phổ biến
- Ethernet Frame (IEEE 802.3) – Sử dụng trong mạng LAN
- PPP Frame (Point-to-Point Protocol) – Dùng trong kết nối Internet
- HDLC Frame (High-Level Data Link Control) – Dùng trong WAN
- Frame Relay – Dùng trong mạng tốc độ cao

Chức năng của Frame trong Data Link Layer
- ✅ Chia nhỏ dữ liệu để truyền dễ dàng hơn
- ✅ Gửi và nhận thông tin dựa trên địa chỉ MAC
- ✅ Phát hiện và sửa lỗi dữ liệu bằng CRC
- ✅ Kiểm soát luồng dữ liệu giữa các thiết bị

---

### Phát hiện và sửa lỗi (Error Detection & Correction)
- **Phát hiện lỗi**: Kiểm tra dữ liệu bị lỗi bằng các phương pháp như Parity Check, Checksum, và CRC.
- **Sửa lỗi**: Khắc phục lỗi bằng các kỹ thuật như Hamming Code.

---

### Điều khiển luồng dữ liệu (Flow Control)
Các cơ chế điều khiển luồng phổ biến:
- **Dừng và chờ (Stop and Wait ARQ)**: Người gửi chờ phản hồi trước khi gửi khung tiếp theo.
- **Cửa sổ trượt (Sliding Window Protocol)**:
  - **Go-Back-N**: Gửi lại tất cả khung sau khi phát hiện lỗi.
  - **Selective Repeat**: Chỉ gửi lại khung bị lỗi.

---

### Piggybacking
Piggybacking giúp tối ưu hóa bằng cách gửi kèm dữ liệu trong các gói phản hồi thay vì gửi riêng lẻ.

---

### Các giao thức Tầng Liên kết Dữ liệu (Data Link Layer Protocols)
Các giao thức phổ biến hoạt động ở tầng này:
- **Ethernet (IEEE 802.3)**: Chuẩn kết nối mạng có dây.
- **Wi-Fi (IEEE 802.11)**: Chuẩn kết nối mạng không dây.
- **PPP (Point-to-Point Protocol)**: Dùng trong kết nối trực tiếp.
- **HDLC (High-Level Data Link Control)**: Giao thức liên kết dữ liệu đồng bộ.

---

Tài liệu này cung cấp thông tin chi tiết về tầng Liên kết Dữ liệu trong mô hình OSI với các khái niệm quan trọng và chức năng của nó.

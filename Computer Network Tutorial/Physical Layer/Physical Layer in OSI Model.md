# Physical Layer in OSI Model

## Introduction
The Physical Layer is the bottom-most layer in the Open System Interconnection (OSI) Model, providing a physical and electrical representation of the system. It consists of various network components such as power plugs, connectors, receivers, and cable types. The physical layer sends data bits from one device (like a computer) to another device.

The Physical Layer defines the types of encoding (how 0’s and 1’s are encoded in a signal). It is responsible for the communication of unstructured raw data streams over a physical medium.

## Functions Performed by Physical Layer
- **Transmission of raw bits:** Converts data into signals that can travel through transmission media and turns signals back into data at the receiver.
- **Encoding and decoding:** Defines how bits are represented in signals.
- **Modulation and demodulation:** Prepares data for transmission and retrieves it at the other end.
- **Transmission modes:** Determines data flow (simplex, half-duplex, or full-duplex).
- **Synchronization:** Controls speed and timing of data transmission.
- **Error detection and correction (basic level):** Ensures signals are transmitted correctly.

---

## Physical Topologies
The arrangement of devices in a network defines its topology. Common topologies include:
- **Bus topology:** A single central cable to which all network devices are connected.
- **Star topology:** Each device connects to a central switch/hub.
- **Ring topology:** Devices are connected in a closed loop.
- **Mesh topology:** Every device is connected to every other device.
- **Hybrid topology:** Combination of two or more topologies.

---

## Modes of Transmission Medium
Transmission modes define how data flows between devices:
- **Simplex:** Data flows in only one direction.
- **Half-duplex:** Data flows in both directions but one at a time.
- **Full-duplex:** Data flows in both directions simultaneously.

---

## Protocols in Physical Layer
Several protocols operate at the physical layer to define standards for data transmission:
- **Ethernet (IEEE 802.3):** Defines wired LAN communication.
- **Wi-Fi (IEEE 802.11):** Defines wireless LAN communication.
- **Bluetooth (IEEE 802.15):** Wireless short-range communication.
- **DSL (Digital Subscriber Line):** High-speed internet over telephone lines.

---

## Types of Transmission Media
Transmission media carry data signals and can be classified as:
### 1. **Guided (Wired) Media:**
- **Twisted-pair cable:** Used in telephone and LANs.
- **Coaxial cable:** Used in cable TV and broadband internet.
- **Fiber optic cable:** High-speed data transmission using light.

### 2. **Unguided (Wireless) Media:**
- **Radio waves:** Used in Wi-Fi and Bluetooth.
- **Microwaves:** Used in satellite and point-to-point communication.
- **Infrared waves:** Used in remote controls and short-range communication.

---

# Tầng Vật Lý trong Mô Hình OSI

## Giới Thiệu
Tầng Vật Lý là tầng thấp nhất trong mô hình Kết Nối Hệ Thống Mở (OSI), cung cấp một biểu diễn vật lý và điện tử của hệ thống. Nó bao gồm các thành phần mạng như phích cắm điện, đầu nối, bộ thu và các loại cáp. Tầng này chịu trách nhiệm truyền các bit dữ liệu từ một thiết bị (như máy tính) đến thiết bị khác.

Tầng Vật Lý xác định các loại mã hóa (cách mã hóa 0 và 1 trong tín hiệu). Nó chịu trách nhiệm truyền các luồng dữ liệu thô chưa cấu trúc qua phương tiện truyền dẫn vật lý.

## Chức Năng của Tầng Vật Lý
- **Truyền bit thô:** Chuyển đổi dữ liệu thành tín hiệu để truyền qua môi trường mạng và chuyển tín hiệu thành dữ liệu tại bộ nhận.
- **Mã hóa và giải mã:** Định nghĩa cách biểu diễn các bit trong tín hiệu.
- **Điều chế và giải điều chế:** Chuẩn bị dữ liệu để truyền và truy xuất nó ở đầu nhận.
- **Chế độ truyền dữ liệu:** Xác định cách dữ liệu được truyền (đơn công, bán song công hoặc song công toàn phần).
- **Đồng bộ hóa:** Kiểm soát tốc độ và thời gian truyền dữ liệu.
- **Phát hiện và sửa lỗi (mức cơ bản):** Đảm bảo tín hiệu được truyền chính xác.

---

## Các Loại Topology Vật Lý
Bố cục thiết bị trong một mạng xác định topology của nó. Các topology phổ biến gồm:
- **Topology Bus:** Một cáp trung tâm kết nối tất cả các thiết bị mạng.
- **Topology Star:** Mỗi thiết bị kết nối với một switch/hub trung tâm.
- **Topology Ring:** Các thiết bị kết nối theo một vòng khép kín.
- **Topology Mesh:** Mỗi thiết bị được kết nối với tất cả các thiết bị khác.
- **Topology Hybrid:** Kết hợp hai hoặc nhiều topology.

---

## Chế Độ Truyền Dữ Liệu
Chế độ truyền dữ liệu xác định cách dữ liệu luân chuyển giữa các thiết bị:
- **Đơn công (Simplex):** Dữ liệu chỉ truyền theo một hướng.
- **Bán song công (Half-duplex):** Dữ liệu truyền theo cả hai hướng nhưng chỉ một chiều tại một thời điểm.
- **Song công toàn phần (Full-duplex):** Dữ liệu truyền theo cả hai hướng cùng lúc.

---

## Các Giao Thức ở Tầng Vật Lý
Một số giao thức hoạt động tại tầng vật lý để xác định tiêu chuẩn truyền dữ liệu:
- **Ethernet (IEEE 802.3):** Định nghĩa truyền thông có dây trong mạng LAN.
- **Wi-Fi (IEEE 802.11):** Định nghĩa truyền thông không dây trong mạng LAN.
- **Bluetooth (IEEE 802.15):** Truyền thông không dây trong khoảng cách ngắn.
- **DSL (Digital Subscriber Line):** Internet tốc độ cao qua đường dây điện thoại.

---

## Các Loại Phương Tiện Truyền Dẫn
Phương tiện truyền dẫn mang tín hiệu dữ liệu và được phân thành:
### 1. **Môi Trường Có Dây (Guided Media):**
- **Cáp xoắn đôi (Twisted-pair cable):** Dùng trong điện thoại và mạng LAN.
- **Cáp đồng trục (Coaxial cable):** Dùng trong truyền hình cáp và internet băng thông rộng.
- **Cáp quang (Fiber optic cable):** Truyền dữ liệu tốc độ cao bằng ánh sáng.

### 2. **Môi Trường Không Dây (Unguided Media):**
- **Sóng vô tuyến (Radio waves):** Dùng trong Wi-Fi và Bluetooth.
- **Vi sóng (Microwaves):** Dùng trong vệ tinh và truyền thông điểm-điểm.
- **Sóng hồng ngoại (Infrared waves):** Dùng trong điều khiển từ xa và truyền thông cự ly ngắn.

---

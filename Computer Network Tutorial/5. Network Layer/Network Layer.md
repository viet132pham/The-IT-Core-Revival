# Network Layer

## Network Layer
The Network Layer is the third layer of the OSI model. It is responsible for routing packets between different networks and determining the best path for data transmission.

---

## Classful Network Addressing
Classful addressing divides IP addresses into five classes: A, B, C, D, and E. Each class has a fixed subnet mask and a predefined number of hosts.

**Example:**
- Class A: IP 10.0.0.1, Subnet Mask: 255.0.0.0
- Class B: IP 172.16.0.1, Subnet Mask: 255.255.0.0
- Class C: IP 192.168.1.1, Subnet Mask: 255.255.255.0

---

## Classless Network Addressing
Classless Inter-Domain Routing (CIDR) allows more flexible IP address allocation by removing fixed subnet masks.

**Example:**
- IP: 192.168.1.1/28 (Subnet Mask: 255.255.255.240)
- Allows 16 addresses instead of a full Class C block.

---

## What is an IP address?
An IP address is a unique identifier assigned to a device in a network, enabling communication between devices.

**Example:**
- 192.168.1.10 (IPv4)
- 2001:db8::ff00:42:8329 (IPv6)

---

## IPv4 Header Format
The IPv4 header contains fields such as source IP, destination IP, version, TTL (Time to Live), and checksum.

---

## IPv4 vs IPv6
| Feature | IPv4 | IPv6 |
|---------|------|------|
| Address Length | 32-bit | 128-bit |
| Address Format | Decimal | Hexadecimal |
| Example | 192.168.1.1 | 2001:db8::ff00:42:8329 |

- IPv4 has limited addresses, whereas IPv6 expands the address space.
- IPv6 supports better security and auto-configuration.

---

## Private vs Public IP addresses
- **Private IP:** Used within local networks (e.g., 192.168.1.1, 10.0.0.1).
- **Public IP:** Used for communication over the Internet (e.g., 8.8.8.8 - Google DNS).

---

## Subnetting
Subnetting divides a large network into smaller segments to optimize performance and security.

**Example:**
- Subnet Mask: 255.255.255.192 (/26)
- Allows 62 usable host addresses instead of 254.

---

## Subnet Masks
A subnet mask helps distinguish the network and host portions of an IP address.

**Example:**
- 255.255.255.0 (/24) – 256 total addresses
- 255.255.255.192 (/26) – 64 total addresses

---

## Variable Length Subnet Masking (VLSM)
VLSM allows networks to be divided into subnets of different sizes for efficient IP allocation.

---

## Supernetting
Supernetting combines multiple small networks into a larger network to reduce the size of routing tables.

---

## Routing
Routing is the process of forwarding packets between different networks. It determines the best path for data transmission.

---

## Static vs Dynamic Routing
- **Static Routing:** Manually configured routes.
- **Dynamic Routing:** Uses protocols to automatically update routing tables.

---

## Link State Routing vs Distance Vector Routing
- **Link State Routing:** Uses a complete network map (e.g., OSPF, IS-IS).
- **Distance Vector Routing:** Uses hop count to determine the best path (e.g., RIP).

---

## Network Address Translation (NAT)
NAT maps private IP addresses to public IP addresses to enable Internet access.

**Example:**
- Private IP: 192.168.1.10 ⇒ Public IP: 203.0.113.5

---

## Network Layer Protocols

### Address Resolution Protocol (ARP)
Resolves IP addresses to MAC addresses for local network communication.

### Reverse Address Resolution Protocol (RARP)
Resolves MAC addresses to IP addresses, opposite of ARP.

### Dynamic Host Configuration Protocol (DHCP)
Automatically assigns IP addresses to devices in a network.

### Internet Control Message Protocol (ICMP)
Used for network diagnostics and error reporting (e.g., ping command).

### Internet Group Management Protocol (IGMP)
Manages multicast group memberships in IPv4 networks.

### Routing Information Protocol (RIP)
A distance-vector routing protocol that determines the best path based on hop count.

### Open Shortest Path First (OSPF)
A link-state routing protocol that finds the shortest path in large networks.

### Intermediate System to Intermediate System (IS-IS)
A link-state routing protocol similar to OSPF, often used by large ISPs.

### Enhanced Interior Gateway Routing Protocol (EIGRP)
A Cisco proprietary routing protocol combining distance-vector and link-state features.

### Border Gateway Protocol (BGP)
The backbone of the Internet, used to exchange routing information between ISPs.

### Multiprotocol Label Switching (MPLS)
Improves network efficiency by directing packets based on labels rather than IP addresses.

### Internet Protocol (IP)
The fundamental protocol for addressing and routing data between networks.

### Generic Routing Encapsulation (GRE)
Encapsulates data to create a virtual point-to-point connection.

---

# Tầng Mạng

*(Translated version in Vietnamese follows here...)*
# Network Layer (Tầng Mạng)

## Network Layer (Tầng Mạng)
Tầng Mạng là tầng thứ ba trong mô hình OSI. Nó chịu trách nhiệm định tuyến các gói dữ liệu giữa các mạng khác nhau và xác định con đường tốt nhất để truyền dữ liệu.

🚀 Chức năng chính của Network Layer:
✔️ Định tuyến (Routing): Tìm đường đi tốt nhất cho dữ liệu đến đích.
✔️ Chuyển tiếp gói tin (Packet Forwarding): Gửi gói tin từ nguồn đến đích.
✔️ Địa chỉ IP (Logical Addressing): Xác định địa chỉ nguồn và địa chỉ đích.
✔️ Kiểm soát tắc nghẽn (Congestion Control): Giảm tải mạng khi lưu lượng cao.
✔️ Chia nhỏ gói tin (Fragmentation & Reassembly): Chia nhỏ và tái lắp ráp gói tin nếu cần.

---

## Classful Network Addressing (Hệ thống định địa chỉ IP theo lớp)
Hệ thống địa chỉ IP theo lớp chia IP thành năm lớp: A, B, C, D, và E. Mỗi lớp có một subnet mask cố định và số lượng host nhất định.

**Ví dụ:**
- Lớp A: IP 10.0.0.1, Subnet Mask: 255.0.0.0
- Lớp B: IP 172.16.0.1, Subnet Mask: 255.255.0.0
- Lớp C: IP 192.168.1.1, Subnet Mask: 255.255.255.0

---

## Classless Network Addressing (Hệ thống định địa chỉ IP không theo lớp)
Định địa chỉ không theo lớp (CIDR) cho phép phân bổ địa chỉ IP linh hoạt hơn bằng cách loại bỏ subnet mask cố định.

**Ví dụ:**
- IP: 192.168.1.1/28 (Subnet Mask: 255.255.255.240)
- Cho phép 16 địa chỉ thay vì một khối lớp C đầy đủ.

---

## What is an IP address? (Địa chỉ IP là gì?)
Địa chỉ IP là một định danh duy nhất được gán cho một thiết bị trong mạng, cho phép các thiết bị liên lạc với nhau.

**Ví dụ:**
- 192.168.1.10 (IPv4)
- 2001:db8::ff00:42:8329 (IPv6)

---

## IPv4 Header Format (Cấu trúc Header IPv4)
Header IPv4 chứa các trường như IP nguồn, IP đích, phiên bản, TTL (thời gian sống) và checksum.

---

## IPv4 vs IPv6 (So sánh IPv4 và IPv6)
| Đặc điểm | IPv4 | IPv6 |
|---------|------|------|
| Độ dài địa chỉ | 32-bit | 128-bit |
| Định dạng địa chỉ | Thập phân | Thập lục phân |
| Ví dụ | 192.168.1.1 | 2001:db8::ff00:42:8329 |

- IPv4 có số lượng địa chỉ hạn chế, trong khi IPv6 mở rộng không gian địa chỉ.
- IPv6 hỗ trợ bảo mật tốt hơn và tự động cấu hình.

---

## Private vs Public IP addresses (Địa chỉ IP riêng và IP công khai)
- **IP riêng:** Dùng trong mạng nội bộ (VD: 192.168.1.1, 10.0.0.1).
- **IP công khai:** Dùng để giao tiếp qua Internet (VD: 8.8.8.8 - Google DNS).

---

## Subnetting (Chia mạng con)
Chia mạng con giúp phân chia mạng lớn thành các phân đoạn nhỏ hơn để tối ưu hóa hiệu suất và bảo mật.

**Ví dụ:**
- Subnet Mask: 255.255.255.192 (/26)
- Cho phép 62 địa chỉ host khả dụng thay vì 254.

---

## Subnet Masks (Mặt nạ mạng con)
Mặt nạ mạng con giúp phân biệt phần mạng và phần host của địa chỉ IP.

**Ví dụ:**
- 255.255.255.0 (/24) – 256 địa chỉ tổng cộng
- 255.255.255.192 (/26) – 64 địa chỉ tổng cộng

---

## Variable Length Subnet Masking (VLSM) (Mặt nạ mạng con có độ dài thay đổi)
VLSM cho phép chia một mạng thành các subnet có kích thước khác nhau để tối ưu hóa phân bổ địa chỉ.

---

## Supernetting (Siêu mạng)
Siêu mạng là quá trình kết hợp nhiều mạng nhỏ thành một mạng lớn hơn để giảm kích thước bảng định tuyến.

---

## Routing (Định tuyến)
Định tuyến là quá trình chuyển tiếp các gói dữ liệu từ mạng này sang mạng khác. Nó xác định đường đi tốt nhất để truyền dữ liệu.

---

## Static vs Dynamic Routing (Định tuyến tĩnh vs động)
- **Định tuyến tĩnh:** Cấu hình thủ công các tuyến đường.
- **Định tuyến động:** Sử dụng giao thức để tự động cập nhật bảng định tuyến.

---

## Link State Routing vs Distance Vector Routing (Định tuyến trạng thái liên kết vs định tuyến vectơ khoảng cách)
- **Định tuyến trạng thái liên kết:** Dùng bản đồ đầy đủ của mạng (VD: OSPF, IS-IS).
- **Định tuyến vectơ khoảng cách:** Sử dụng số lượng bước nhảy để xác định đường đi (VD: RIP).

---

## Network Address Translation (NAT) (Dịch địa chỉ mạng)
NAT ánh xạ địa chỉ IP riêng sang địa chỉ IP công khai để cho phép truy cập Internet.

**Ví dụ:**
- IP riêng: 192.168.1.10 ⇒ IP công khai: 203.0.113.5

---

## Network Layer Protocols (Các giao thức tầng mạng)

### Address Resolution Protocol (ARP) (Giao thức phân giải địa chỉ)
Chuyển đổi địa chỉ IP thành địa chỉ MAC để liên lạc trong mạng cục bộ.

### Reverse Address Resolution Protocol (RARP) (Giao thức phân giải địa chỉ ngược)
Chuyển đổi địa chỉ MAC thành địa chỉ IP, ngược lại với ARP.

### Dynamic Host Configuration Protocol (DHCP) (Giao thức cấu hình động máy chủ)
Tự động gán địa chỉ IP cho các thiết bị trong mạng.

### Internet Control Message Protocol (ICMP) (Giao thức điều khiển thông điệp Internet)
Dùng để chẩn đoán mạng và báo lỗi (VD: lệnh ping).

### Internet Group Management Protocol (IGMP) (Giao thức quản lý nhóm Internet)
Quản lý các nhóm multicast trong mạng IPv4.

### Routing Information Protocol (RIP) (Giao thức thông tin định tuyến)
Giao thức định tuyến vectơ khoảng cách sử dụng số lượng bước nhảy để tìm đường tốt nhất.

### Open Shortest Path First (OSPF) (Giao thức định tuyến OSPF)
Giao thức định tuyến trạng thái liên kết tìm đường ngắn nhất trong mạng lớn.

### Intermediate System to Intermediate System (IS-IS) (Giao thức IS-IS)
Giao thức định tuyến trạng thái liên kết tương tự OSPF, thường dùng trong ISP lớn.

### Enhanced Interior Gateway Routing Protocol (EIGRP) (Giao thức định tuyến nâng cao của Cisco)
Giao thức định tuyến của Cisco kết hợp đặc điểm của định tuyến vectơ khoảng cách và trạng thái liên kết.

### Border Gateway Protocol (BGP) (Giao thức cổng biên)
Xương sống của Internet, dùng để trao đổi thông tin định tuyến giữa các ISP.

### Multiprotocol Label Switching (MPLS) (Chuyển mạch nhãn đa giao thức)
Cải thiện hiệu suất mạng bằng cách định hướng gói dữ liệu dựa trên nhãn thay vì địa chỉ IP.

### Internet Protocol (IP) (Giao thức Internet)
Giao thức cơ bản để định địa chỉ và định tuyến dữ liệu giữa các mạng.

### Generic Routing Encapsulation (GRE) (Giao thức đóng gói GRE)
Đóng gói dữ liệu để tạo kết nối ảo giữa hai điểm.

---

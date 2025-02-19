# 📡 Basics of Computer Networking

## 🏆 How Does a Computer Network Work?
Basics building blocks of a Computer network are Nodes and Links. A Network Node can be illustrated as Equipment for Data Communication like a Modem, Router, etc., or Equipment of a Data Terminal like connecting two computers or more. Link in Computer Networks can be defined as wires or cables or free space of wireless networks.

The working of Computer Networks can be simply defined as rules or protocols which help in sending and receiving data via the links which allow Computer networks to communicate. Each device has an IP Address, that helps in identifying a device.

---

## 🌐 What do Computer Networks do?
- Work Virtually: The physical network can be divided into smaller virtual networks. In these virtual networks, devices are connected and can send data through multiple physical routes. For example, many business networks use the internet this way.
- Connect on a Large Scale: Modern networks link many smaller, spread-out networks into one big, powerful system. Automation and monitoring tools help manage and adjust the network as needed, allowing it to grow or shrink based on demand.
- Adapt Quickly: Many networks are controlled by software, so changes can be made quickly through a digital dashboard. This allows traffic to be managed easily.
- Keep Data Secure: Built-in security features like encryption and access control protect data. Additional protections like antivirus software, firewalls, and malware protection can be added to strengthen network security.
---

## 🌍 Basic Terminologies of Computer Networks
- Network: A network is a collection of computers and devices that are connected together to enable communication and data exchange.
- Nodes: Nodes are devices that are connected to a network. These can include computers, Servers, Printers, Routers, Switches, and other devices.
- Protocol: A protocol is a set of rules and standards that govern how data is transmitted over a network. Examples of protocols include TCP/IP, HTTP, and FTP.
- Topology: Network topology refers to the physical and logical arrangement of nodes on a network. The common network topologies include bus, star, ring, mesh, and tree.
- Service Provider Networks: These types of Networks give permission to take Network Capacity and Functionality on lease from the Provider. Service Provider Networks include Wireless Communications, Data Carriers, etc.
- IP Address: An IP address is a unique numerical identifier that is assigned to every device on a network. IP addresses are used to identify devices and enable communication between them.
- DNS: The Domain Name System (DNS) is a protocol that is used to translate human-readable domain names (such as www.google.com) into IP addresses that computers can understand.
- Firewall: A firewall is a security device that is used to monitor and control incoming and outgoing network traffic. Firewalls are used to protect networks from unauthorized access and other security threats.

---

## 🔗 Types of Enterprise Computer Networks
- LAN: A Local Area Network (LAN) is a network that covers a small area, such as an office or a home. LANs are typically used to connect computers and other devices within a building or a campus.
- WAN: A Wide Area Network (WAN) is a network that covers a large geographic area, such as a city, country, or even the entire world. WANs are used to connect LANs together and are typically used for long-distance communication.
- Cloud Networks: Cloud Networks can be visualized with a Wide Area Network (WAN) as they can be hosted on public or private cloud service providers and cloud networks are available if there is a demand. Cloud Networks consist of Virtual Routers, Firewalls, etc.
---

## 🔗 Types of Computer Network Architecture
- Client-Server Architecture: Client-Server Architecture is a type of Computer Network Architecture in which Nodes can be Servers or Clients. Here, the server node can manage the Client Node Behaviour.
- Peer-to-Peer Architecture: In P2P (Peer-to-Peer) Architecture, there is not any concept of a Central Server. Each device is free for working as either client or server.

---

## 📡 Network Devices
An interconnection of multiple devices, also known as hosts, that are connected using multiple paths for the purpose of sending/receiving data or media. Computer networks can also include multiple devices/mediums which help in the communication between two different devices; these are known as Network devices and include things such as routers, switches, hubs, and bridges. 
<p align="center">
  <img src="../../images/Computer Network Tutorial/Fundamentals of Computer Network/router-hub.jpg" alt="Network Devices">
</p>

## Network Topology
- Bus Topology: In bus topology all devices are connected to a single central cable called a bus. Data is sent along this cable and all devices share the same connection. Simple and cheap to set up but if the main cable fails the whole network goes down.
- Star Topology: In star topology all devices are connected to a central node called hub or switch. The hub controls the flow of data between devices. If one device fails the rest of the network is unaffected. But, if the central hub fails the whole network stops working.
- Ring Topology: In ring topology devices are connected in a circular loop with each device connected to two others. Data travels in one direction (or sometimes both) passing through each device until it reaches its destination. A failure in one device can affect the whole network.
- Mesh Topology: In mesh topology every device is connected to every other device in the network. It provides multiple paths for data so if one path fails another can take over.
- Tree Topology: Tree topology is the combination of star and bus topology. Tree topology is good for organizing large networks and allows for easy expansion.
- Hybrid Topology: Hybrid topology is the combination of two or more different topologies (like star and mesh). It is flexible and can be customized based on the network’s specific needs.
<p align="center">
  <img src="../../images/Computer Network Tutorial/Fundamentals of Computer Network/STAR-MESH.jpg" alt="Network Topology">
</p>

## OSI Model  
- Physical Layer
- Data link Layer
- Network Layer
- Transport Layer
- Session Layer
- Presentation Layer
- Application Layer

## Network Protocols 
- Transmission Control Protocol/Internet Protocol (TCP/IP): TCP/IP is the foundational protocol suite of the internet, enabling reliable communication. TCP Ensures data is delivered reliably and in order and IP routes data packets to their destination based on IP addresses.
- Hypertext Transfer Protocol (HTTP) and HTTPS: HTTP and HTTPS protocols used for transmitting web pages. In HTTP communication is unsecured and in HTTPS secured communication using SSL/TLS encryption.
- Simple Mail Transfer Protocol (SMTP): SMTP protocol used to send email. SMTP protocol works with other protocols like POP3 and IMAP for email retrieval.
- File Transfer Protocol (FTP): FTP protocol used for transferring files between computers. Includes commands for uploading, downloading, and managing files on a remote server.
- Dynamic Host Configuration Protocol (DHCP): DHCP protocol automatically assigns IP addresses to devices on a network. Reduces manual configuration and IP address conflicts.
- Domain Name System (DNS): DNS Translates human-friendly domain names into IP addresses. Ensures seamless navigation on the internet.

---

## What is the difference between TCP and UDP?
- TCP (Transmission Control Protocol): A connection-oriented protocol that ensures reliable and ordered delivery of data. It is used for applications where data integrity is critical, like web browsing and email.
- UDP (User Datagram Protocol): A connectionless protocol that does not guarantee delivery or order. It is used for applications where speed is more important than reliability, like streaming and gaming.

---

# 📡 Cơ bản về mạng máy tính 

## 🏆 Mạng máy tính hoạt động như thế nào?
Các khối xây dựng cơ bản của mạng máy tính là các nút và liên kết. Nút mạng có thể được minh họa là thiết bị truyền dữ liệu như Modem, Bộ định tuyến, v.v. hoặc thiết bị đầu cuối dữ liệu như kết nối hai máy tính trở lên. Liên kết trong mạng máy tính có thể được định nghĩa là dây hoặc cáp hoặc không gian trống của mạng không dây.

Hoạt động của Mạng máy tính có thể được định nghĩa đơn giản là các quy tắc hoặc giao thức giúp gửi và nhận dữ liệu qua các liên kết cho phép Mạng máy tính giao tiếp. Mỗi thiết bị có một Địa chỉ IP, giúp xác định thiết bị.

---

## 🌐 Mạng máy tính có chức năng gì?
- Làm việc ảo: Mạng vật lý có thể được chia thành các mạng ảo nhỏ hơn . Trong các mạng ảo này, các thiết bị được kết nối và có thể gửi dữ liệu qua nhiều tuyến vật lý. Ví dụ, nhiều mạng doanh nghiệp sử dụng internet theo cách này.
- Kết nối trên quy mô lớn: Các mạng hiện đại liên kết nhiều mạng nhỏ hơn, phân tán thành một hệ thống lớn, mạnh mẽ. Các công cụ tự động hóa và giám sát giúp quản lý và điều chỉnh mạng khi cần, cho phép mạng phát triển hoặc thu hẹp tùy theo nhu cầu.
- Thích ứng nhanh chóng: Nhiều mạng được điều khiển bằng phần mềm, do đó có thể thực hiện thay đổi nhanh chóng thông qua bảng điều khiển kỹ thuật số. Điều này cho phép quản lý lưu lượng dễ dàng.
- Giữ dữ liệu an toàn: Các tính năng bảo mật tích hợp như mã hóa và kiểm soát truy cập bảo vệ dữ liệu. Các biện pháp bảo vệ bổ sung như phần mềm diệt vi-rút, tường lửa và bảo vệ phần mềm độc hại có thể được thêm vào để tăng cường bảo mật mạng.

---

## 🌍 Thuật ngữ cơ bản của mạng máy tính
- Mạng: Mạng là tập hợp các máy tính và thiết bị được kết nối với nhau để cho phép truyền thông và trao đổi dữ liệu.
- Node: Node là các thiết bị được kết nối với mạng. Chúng có thể bao gồm máy tính, Máy chủ, Máy in, Bộ định tuyến, Bộ chuyển mạch và các thiết bị khác.
- Giao thức: Giao thức là một tập hợp các quy tắc và tiêu chuẩn chi phối cách dữ liệu được truyền qua mạng. Ví dụ về giao thức bao gồm TCP/IP, HTTP và FTP .
- Topology: Topology mạng đề cập đến sự sắp xếp vật lý và logic của các nút trên mạng. Các topology mạng phổ biến bao gồm bus, star, ring, mesh và tree.
- Mạng của Nhà cung cấp dịch vụ: Các loại Mạng này cấp quyền thuê Năng lực và Chức năng Mạng từ Nhà cung cấp. Mạng của Nhà cung cấp dịch vụ bao gồm Truyền thông không dây, Nhà cung cấp dữ liệu, v.v.
- Địa chỉ IP : Địa chỉ IP là mã định danh số duy nhất được gán cho mọi thiết bị trên mạng. Địa chỉ IP được sử dụng để xác định các thiết bị và cho phép giao tiếp giữa chúng.
- DNS: Hệ thống tên miền (DNS) là một giao thức được sử dụng để dịch các tên miền mà con người có thể đọc được (như www.google.com) thành địa chỉ IP mà máy tính có thể hiểu được.
- Tường lửa: Tường lửa là thiết bị bảo mật được sử dụng để giám sát và kiểm soát lưu lượng mạng đến và đi. Tường lửa được sử dụng để bảo vệ mạng khỏi truy cập trái phép và các mối đe dọa bảo mật khác.

---

## 🔗 Các loại mạng máy tính doanh nghiệp
- LAN: Mạng cục bộ (LAN) là mạng bao phủ một khu vực nhỏ, chẳng hạn như văn phòng hoặc nhà riêng. LAN thường được sử dụng để kết nối máy tính và các thiết bị khác trong một tòa nhà hoặc khuôn viên trường.
- WAN: Mạng diện rộng (WAN) là mạng bao phủ một khu vực địa lý rộng lớn, chẳng hạn như một thành phố, một quốc gia hoặc thậm chí toàn thế giới. WAN được sử dụng để kết nối các mạng LAN với nhau và thường được sử dụng cho truyền thông đường dài.
- Mạng đám mây: Mạng đám mây có thể được hình dung bằng Mạng diện rộng (WAN) vì chúng có thể được lưu trữ trên các nhà cung cấp dịch vụ đám mây công cộng hoặc riêng tư và mạng đám mây có sẵn nếu có nhu cầu. Mạng đám mây bao gồm Bộ định tuyến ảo, Tường lửa, v.v.

---

## 🔗 Các loại kiến ​​trúc mạng máy tính
- Kiến trúc máy khách-máy chủ: Kiến trúc máy khách-máy chủ là một loại Kiến trúc mạng máy tính trong đó các nút có thể là máy chủ hoặc máy khách. Ở đây, nút máy chủ có thể quản lý Hành vi của nút máy khách.
- Kiến trúc ngang hàng: Trong Kiến trúc ngang hàng (Peer-to-Peer) , không có khái niệm nào về Máy chủ trung tâm. Mỗi thiết bị đều có thể hoạt động như máy khách hoặc máy chủ.

---

## 📡 Thiết bị mạng
Sự kết nối của nhiều thiết bị, còn được gọi là máy chủ, được kết nối bằng nhiều đường dẫn nhằm mục đích gửi/nhận dữ liệu hoặc phương tiện. Mạng máy tính cũng có thể bao gồm nhiều thiết bị/phương tiện giúp giao tiếp giữa hai thiết bị khác nhau; chúng được gọi là thiết bị mạng và bao gồm những thứ như bộ định tuyến, bộ chuyển mạch, bộ chia và cầu nối. 
<p align="center">
  <img src="../../images/Computer Network Tutorial/Fundamentals of Computer Network/router-hub.jpg" alt="Network Devices">
</p>

## Cấu trúc mạng
- Bus Topology: Trong bus topology, tất cả các thiết bị được kết nối với một cáp trung tâm duy nhất gọi là bus. Dữ liệu được gửi dọc theo cáp này và tất cả các thiết bị chia sẻ cùng một kết nối. Đơn giản và rẻ để thiết lập nhưng nếu cáp chính bị hỏng thì toàn bộ mạng sẽ ngừng hoạt động.
- Star Topology: Trong star topology, tất cả các thiết bị được kết nối với một nút trung tâm gọi là hub hoặc switch. Hub điều khiển luồng dữ liệu giữa các thiết bị. Nếu một thiết bị hỏng, phần còn lại của mạng sẽ không bị ảnh hưởng. Nhưng nếu hub trung tâm hỏng, toàn bộ mạng sẽ ngừng hoạt động.
- Topology vòng : Trong topology vòng, các thiết bị được kết nối trong một vòng tròn với mỗi thiết bị được kết nối với hai thiết bị khác. Dữ liệu di chuyển theo một hướng (hoặc đôi khi là cả hai hướng) đi qua từng thiết bị cho đến khi đến đích. Một lỗi ở một thiết bị có thể ảnh hưởng đến toàn bộ mạng.
- Cấu trúc lưới : Trong cấu trúc lưới, mọi thiết bị đều được kết nối với mọi thiết bị khác trong mạng. Nó cung cấp nhiều đường dẫn cho dữ liệu để nếu một đường dẫn bị lỗi, đường dẫn khác có thể tiếp quản.
- Tree Topology : Tree Topology là sự kết hợp giữa star và bus topology. Tree Topology thích hợp cho việc tổ chức các mạng lớn và cho phép mở rộng dễ dàng.
- Hybrid Topology : Hybrid Topology là sự kết hợp của hai hoặc nhiều topology khác nhau (như star và mesh). Nó linh hoạt và có thể tùy chỉnh dựa trên nhu cầu cụ thể của mạng.
<p align="center">
  <img src="../../images/Computer Network Tutorial/Fundamentals of Computer Network/STAR-MESH.jpg" alt="Network Topology">
</p>

## Mô hình OSI 
- Lớp vật lý
- Lớp liên kết dữ liệu
- Lớp mạng
- Lớp vận chuyển
- Lớp phiên
- Lớp trình bày
- Lớp ứng dụng

## Giao thức mạng
- Giao thức điều khiển truyền/Giao thức Internet (TCP/IP): TCP/IP là bộ giao thức nền tảng của internet, cho phép truyền thông tin cậy. TCP đảm bảo dữ liệu được truyền đi một cách đáng tin cậy và theo thứ tự, còn IP định tuyến các gói dữ liệu đến đích dựa trên địa chỉ IP.
- Giao thức truyền siêu văn bản (HTTP) và HTTPS: Giao thức HTTP và HTTPS được sử dụng để truyền các trang web. Trong HTTP, giao tiếp không được bảo mật và trong HTTPS, giao tiếp được bảo mật bằng mã hóa SSL/TLS .
- Giao thức truyền thư đơn giản (SMTP): Giao thức SMTP được sử dụng để gửi email. Giao thức SMTP hoạt động với các giao thức khác như POP3 và IMAP để truy xuất email.
- Giao thức truyền tệp (FTP): Giao thức FTP được sử dụng để truyền tệp giữa các máy tính. Bao gồm các lệnh để tải lên, tải xuống và quản lý tệp trên máy chủ từ xa.
- Giao thức cấu hình máy chủ động (DHCP): Giao thức DHCP tự động gán địa chỉ IP cho các thiết bị trên mạng. Giảm cấu hình thủ công và xung đột địa chỉ IP.
- Hệ thống tên miền (DNS): DNS dịch tên miền thân thiện với con người thành địa chỉ IP. Đảm bảo điều hướng liền mạch trên internet.

---

## Sự khác biệt giữa TCP và UDP là gì?
- TCP (Transmission Control Protocol): Giao thức hướng kết nối đảm bảo việc phân phối dữ liệu đáng tin cậy và có thứ tự. Giao thức này được sử dụng cho các ứng dụng mà tính toàn vẹn của dữ liệu là rất quan trọng, như duyệt web và email.
- UDP (User Datagram Protocol): Giao thức không kết nối không đảm bảo việc phân phối hoặc thứ tự. Giao thức này được sử dụng cho các ứng dụng mà tốc độ quan trọng hơn độ tin cậy, như livestream và chơi game.

---

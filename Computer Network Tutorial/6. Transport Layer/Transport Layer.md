# Transport Layer

## Transport Layer (Tầng Giao Vận)
The Transport Layer (Layer 4) is responsible for end-to-end communication, error detection, and data flow control. It ensures that data is transferred reliably and efficiently between devices.

Tầng Giao Vận (Lớp 4) chịu trách nhiệm truyền thông đầu cuối, phát hiện lỗi và kiểm soát luồng dữ liệu. Nó đảm bảo dữ liệu được truyền một cách đáng tin cậy và hiệu quả giữa các thiết bị.

---

## TCP Protocol (Giao thức TCP)
Transmission Control Protocol (TCP) is a connection-oriented protocol that ensures reliable, ordered, and error-checked delivery of data.

**Example:** When you load a webpage or send an email, TCP ensures that all packets arrive correctly and in order.

Giao thức TCP là một giao thức hướng kết nối, đảm bảo dữ liệu được truyền tải một cách đáng tin cậy, có thứ tự và kiểm tra lỗi.

**Ví dụ:** Khi bạn tải một trang web hoặc gửi email, TCP đảm bảo tất cả các gói tin đến đúng và theo thứ tự.

---

## TCP 3-Way Handshake Process (Quy trình bắt tay ba bước của TCP)
The 3-way handshake is the process used by TCP to establish a connection between a client and a server.

1. **SYN:** Client sends a SYN request to start a connection.
2. **SYN-ACK:** Server responds with a SYN-ACK.
3. **ACK:** Client sends an ACK to confirm the connection.

**Example:** When you open a website, your browser (client) initiates a handshake with the web server before data transfer begins.

Quy trình bắt tay ba bước được TCP sử dụng để thiết lập kết nối giữa máy khách và máy chủ.

1. **SYN:** Máy khách gửi yêu cầu SYN để bắt đầu kết nối.
2. **SYN-ACK:** Máy chủ phản hồi bằng một gói SYN-ACK.
3. **ACK:** Máy khách gửi một gói ACK để xác nhận kết nối.

**Ví dụ:** Khi bạn mở một trang web, trình duyệt của bạn (máy khách) thực hiện bắt tay với máy chủ web trước khi dữ liệu được truyền tải.

---

## Services and Segment Structure in TCP (Dịch vụ và cấu trúc phân đoạn trong TCP)
TCP segments contain key fields such as source and destination ports, sequence numbers, acknowledgment numbers, flags, window size, checksum, and data.

**Example:** TCP uses sequence numbers and acknowledgments to ensure no data is lost or duplicated.

Phân đoạn TCP chứa các trường quan trọng như cổng nguồn, cổng đích, số thứ tự, số xác nhận, cờ điều khiển, kích thước cửa sổ, mã kiểm tra và dữ liệu.

**Ví dụ:** TCP sử dụng số thứ tự và xác nhận để đảm bảo không có dữ liệu bị mất hoặc trùng lặp.

---

## TCP Connection Establishment (Thiết lập kết nối TCP)
Connection establishment in TCP follows the 3-way handshake process.

**Example:** When logging into a remote server via SSH, TCP ensures a stable connection before data transfer starts.

Thiết lập kết nối TCP tuân theo quy trình bắt tay ba bước.

**Ví dụ:** Khi đăng nhập vào một máy chủ từ xa qua SSH, TCP đảm bảo một kết nối ổn định trước khi truyền dữ liệu.

---

## TCP Termination (Kết thúc kết nối TCP)
TCP uses a **4-step termination process** to gracefully close a connection.

1. **FIN:** Client sends a FIN packet.
2. **ACK:** Server acknowledges.
3. **FIN:** Server sends its own FIN packet.
4. **ACK:** Client acknowledges, closing the connection.

**Example:** When you close a web browser tab, TCP ensures all pending data is transmitted before ending the connection.

TCP sử dụng một **quy trình kết thúc bốn bước** để đóng kết nối một cách có trật tự.

1. **FIN:** Máy khách gửi một gói FIN.
2. **ACK:** Máy chủ xác nhận.
3. **FIN:** Máy chủ gửi gói FIN của nó.
4. **ACK:** Máy khách xác nhận, kết thúc kết nối.

**Ví dụ:** Khi bạn đóng một tab trình duyệt, TCP đảm bảo rằng tất cả dữ liệu còn lại được truyền trước khi kết thúc kết nối.

---

## Congestion Control in TCP (Kiểm soát tắc nghẽn trong TCP)
TCP prevents network congestion using techniques like **slow start, congestion avoidance, and fast recovery.**

**Example:** When many users stream videos simultaneously, TCP dynamically adjusts data transmission rates to prevent network overload.

TCP ngăn chặn tắc nghẽn mạng bằng các kỹ thuật như **khởi đầu chậm, tránh tắc nghẽn và phục hồi nhanh.**

**Ví dụ:** Khi nhiều người dùng phát video cùng lúc, TCP điều chỉnh tốc độ truyền dữ liệu để tránh quá tải mạng.

---

## UDP Protocol (Giao thức UDP)
User Datagram Protocol (UDP) is a connectionless, lightweight protocol used for fast, low-latency applications.

**Example:** Online gaming and VoIP calls use UDP because speed is prioritized over reliability.

UDP là một giao thức không kết nối, nhẹ, được sử dụng cho các ứng dụng yêu cầu tốc độ và độ trễ thấp.

**Ví dụ:** Trò chơi trực tuyến và cuộc gọi VoIP sử dụng UDP vì ưu tiên tốc độ hơn độ tin cậy.

---

## TCP vs UDP Protocol (So sánh TCP và UDP)
| Feature | TCP | UDP |
|---------|-----|-----|
| Connection Type | Connection-Oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Speed | Slower | Faster |
| Use Cases | Web browsing, emails | Streaming, gaming |

| Đặc điểm | TCP | UDP |
|---------|-----|-----|
| Kiểu kết nối | Có kết nối | Không kết nối |
| Độ tin cậy | Đáng tin cậy | Không đáng tin cậy |
| Tốc độ | Chậm hơn | Nhanh hơn |
| Ứng dụng | Duyệt web, email | Phát trực tuyến, chơi game |

---

## Stream Control Transmission Protocol (SCTP) (Giao thức SCTP)
SCTP combines features of TCP and UDP, providing reliability with multi-streaming capabilities.

**Example:** Used in telecommunications for signaling messages.

SCTP kết hợp các đặc điểm của TCP và UDP, cung cấp độ tin cậy với khả năng truyền dữ liệu đa luồng.

**Ví dụ:** Được sử dụng trong viễn thông để truyền tín hiệu.

---

## Datagram Congestion Control Protocol (DCCP) (Giao thức DCCP)
DCCP balances speed and reliability, used in streaming media applications.

**Example:** Video conferencing applications use DCCP for smooth video playback.

DCCP cân bằng giữa tốc độ và độ tin cậy, được sử dụng trong các ứng dụng truyền phát đa phương tiện.

**Ví dụ:** Các ứng dụng hội nghị truyền hình sử dụng DCCP để phát video mượt mà.

---

## Quick UDP Internet Connections (QUIC) (Giao thức QUIC)
QUIC is a Google-developed transport protocol enhancing speed and security over UDP.

**Example:** QUIC powers Google's services like YouTube for faster video loading.

QUIC là một giao thức do Google phát triển, cải thiện tốc độ và bảo mật trên UDP.

**Ví dụ:** QUIC hỗ trợ các dịch vụ của Google như YouTube để tải video nhanh hơn.

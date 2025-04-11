# Event-Driven Architecture

## English Version

### What is Event-Driven Architecture? (Simple Explanation)
Think of Event-Driven Architecture (EDA) like a party where:
- Instead of people constantly checking on each other, they use a bell to signal important things
- When the bell rings (event happens), people who are interested (consumers) react to it
- Different groups can do different things when they hear the bell
- No one needs to constantly check what others are doing

### Real-World Example: Online Shopping System
Let's look at how an online shopping system works with EDA:

1. **When a Customer Places an Order**
   - Event: "OrderPlaced"
   - What happens:
     * Payment service processes payment
     * Inventory service updates stock
     * Notification service sends confirmation email
     * Shipping service prepares delivery

2. **When Payment is Processed**
   - Event: "PaymentProcessed"
   - What happens:
     * Order status is updated
     * Warehouse is notified to pack items
     * Customer gets payment confirmation

3. **When Item is Shipped**
   - Event: "ItemShipped"
   - What happens:
     * Customer gets shipping notification
     * Analytics service updates delivery metrics
     * Customer service is notified to expect delivery queries

### Key Components (With Simple Examples)

1. **Event Producers** (Things that create events)
   - User actions (clicking "Buy Now")
   - System processes (payment processing)
   - External services (weather updates)
   - Example: When you click "Buy Now", the website creates an "OrderPlaced" event

2. **Event Consumers** (Things that react to events)
   - Notification services (sending emails)
   - Analytics services (tracking sales)
   - Inventory systems (updating stock)
   - Example: When "OrderPlaced" happens, the email service sends a confirmation

3. **Event Channels** (How events travel)
   - Like a post office for events
   - Makes sure events reach the right places
   - Example: Kafka or RabbitMQ act as the "post office"

### Common Patterns (With Everyday Examples)

1. **Publish-Subscribe** (Like a Newspaper)
   - Publisher: Creates news (events)
   - Subscribers: People who want the news
   - Example: 
     * Weather service publishes "RainAlert"
     * Umbrella shop and traffic control both subscribe
     * Both get the alert and take action

2. **Event Streaming** (Like a Live Sports Feed)
   - Continuous flow of updates
   - Real-time processing
   - Example:
     * Stock market updates
     * Live sports scores
     * Social media feeds

3. **Event Sourcing** (Like a Bank Statement)
   - Keeps history of all changes
   - Can replay events to see how things changed
   - Example:
     * Bank account transactions
     * Version control systems
     * Audit trails

### Benefits (With Real Examples)

1. **Loose Coupling**
   - Services don't need to know about each other
   - Example: Email service doesn't need to know about payment processing

2. **Scalability**
   - Easy to add new features
   - Example: Adding a new analytics service without changing existing ones

3. **Real-time Processing**
   - Immediate reactions to events
   - Example: Instant notifications when order status changes

### Common Challenges (With Solutions)

1. **Event Ordering**
   - Problem: Events might arrive in wrong order
   - Solution: Use timestamps and sequence numbers

2. **Error Handling**
   - Problem: What if an event fails?
   - Solution: Use retry mechanisms and dead letter queues

3. **Monitoring**
   - Problem: How to track event flow?
   - Solution: Use tools like Prometheus and Grafana

## Vietnamese Version

### Kiến trúc hướng sự kiện là gì? (Giải thích đơn giản)
Hãy tưởng tượng Kiến trúc hướng sự kiện (EDA) giống như một bữa tiệc:
- Thay vì mọi người liên tục kiểm tra nhau, họ dùng chuông để báo hiệu điều quan trọng
- Khi chuông reo (sự kiện xảy ra), những người quan tâm (người tiêu thụ) sẽ phản ứng
- Các nhóm khác nhau có thể làm những việc khác nhau khi nghe chuông
- Không ai cần liên tục kiểm tra người khác đang làm gì

### Ví dụ thực tế: Hệ thống mua sắm trực tuyến
Hãy xem cách một hệ thống mua sắm trực tuyến hoạt động với EDA:

1. **Khi khách hàng đặt hàng**
   - Sự kiện: "OrderPlaced"
   - Điều gì xảy ra:
     * Dịch vụ thanh toán xử lý thanh toán
     * Dịch vụ kho cập nhật hàng tồn
     * Dịch vụ thông báo gửi email xác nhận
     * Dịch vụ vận chuyển chuẩn bị giao hàng

2. **Khi thanh toán được xử lý**
   - Sự kiện: "PaymentProcessed"
   - Điều gì xảy ra:
     * Trạng thái đơn hàng được cập nhật
     * Kho hàng được thông báo đóng gói
     * Khách hàng nhận được xác nhận thanh toán

3. **Khi hàng được giao**
   - Sự kiện: "ItemShipped"
   - Điều gì xảy ra:
     * Khách hàng nhận được thông báo giao hàng
     * Dịch vụ phân tích cập nhật số liệu giao hàng
     * Dịch vụ khách hàng được thông báo để chuẩn bị trả lời câu hỏi

### Các thành phần chính (Với ví dụ đơn giản)

1. **Nhà sản xuất sự kiện** (Những thứ tạo ra sự kiện)
   - Hành động người dùng (nhấp "Mua ngay")
   - Quy trình hệ thống (xử lý thanh toán)
   - Dịch vụ bên ngoài (cập nhật thời tiết)
   - Ví dụ: Khi bạn nhấp "Mua ngay", website tạo sự kiện "OrderPlaced"

2. **Người tiêu thụ sự kiện** (Những thứ phản ứng với sự kiện)
   - Dịch vụ thông báo (gửi email)
   - Dịch vụ phân tích (theo dõi doanh số)
   - Hệ thống kho (cập nhật hàng tồn)
   - Ví dụ: Khi "OrderPlaced" xảy ra, dịch vụ email gửi xác nhận

3. **Kênh sự kiện** (Cách sự kiện di chuyển)
   - Giống như bưu điện cho sự kiện
   - Đảm bảo sự kiện đến đúng nơi
   - Ví dụ: Kafka hoặc RabbitMQ hoạt động như "bưu điện"

### Mẫu phổ biến (Với ví dụ hàng ngày)

1. **Publish-Subscribe** (Giống như báo chí)
   - Nhà xuất bản: Tạo tin tức (sự kiện)
   - Người đăng ký: Những người muốn tin tức
   - Ví dụ:
     * Dịch vụ thời tiết xuất bản "RainAlert"
     * Cửa hàng ô và kiểm soát giao thông đều đăng ký
     * Cả hai nhận được cảnh báo và hành động

2. **Event Streaming** (Giống như bản tin thể thao trực tiếp)
   - Luồng cập nhật liên tục
   - Xử lý thời gian thực
   - Ví dụ:
     * Cập nhật thị trường chứng khoán
     * Điểm số thể thao trực tiếp
     * Bảng tin mạng xã hội

3. **Event Sourcing** (Giống như sao kê ngân hàng)
   - Lưu lịch sử tất cả thay đổi
   - Có thể phát lại sự kiện để xem mọi thứ thay đổi thế nào
   - Ví dụ:
     * Giao dịch tài khoản ngân hàng
     * Hệ thống kiểm soát phiên bản
     * Dấu vết kiểm toán

### Lợi ích (Với ví dụ thực tế)

1. **Liên kết lỏng lẻo**
   - Các dịch vụ không cần biết về nhau
   - Ví dụ: Dịch vụ email không cần biết về xử lý thanh toán

2. **Khả năng mở rộng**
   - Dễ dàng thêm tính năng mới
   - Ví dụ: Thêm dịch vụ phân tích mới mà không thay đổi dịch vụ hiện có

3. **Xử lý thời gian thực**
   - Phản ứng ngay lập tức với sự kiện
   - Ví dụ: Thông báo tức thì khi trạng thái đơn hàng thay đổi

### Thách thức phổ biến (Với giải pháp)

1. **Thứ tự sự kiện**
   - Vấn đề: Sự kiện có thể đến không đúng thứ tự
   - Giải pháp: Sử dụng dấu thời gian và số thứ tự

2. **Xử lý lỗi**
   - Vấn đề: Nếu sự kiện thất bại thì sao?
   - Giải pháp: Sử dụng cơ chế thử lại và hàng đợi thư chết

3. **Giám sát**
   - Vấn đề: Làm thế nào để theo dõi luồng sự kiện?
   - Giải pháp: Sử dụng công cụ như Prometheus và Grafana 


   # Event-Driven Architecture (EDA)

## English Version

### What is Event-Driven Architecture?
Event-Driven Architecture (EDA) is a software architecture pattern where components communicate through events. Think of it like a modern social media platform's notification system - when something happens (an event), interested parties are notified and can react accordingly.

### Real-World Example: E-commerce Platform (Like Amazon)
Imagine a large e-commerce platform handling millions of transactions:

1. **User Places an Order**
   ```json
   {
     "event": "OrderCreated",
     "data": {
       "orderId": "12345",
       "userId": "user789",
       "items": [
         {"productId": "prod123", "quantity": 2},
         {"productId": "prod456", "quantity": 1}
       ],
       "totalAmount": 150.00
     }
   }
   ```

2. **Multiple Services React**
   - Payment Service: Processes payment
   - Inventory Service: Updates stock levels
   - Notification Service: Sends confirmation emails
   - Analytics Service: Updates sales metrics

### Core Components

1. **Event Producers**
   - Definition: Components that generate and emit events
   - Real Examples:
     * IoT Sensors (Tesla's vehicle sensors)
     * User Interfaces (Netflix's video player)
     * External APIs (Stripe payment webhooks)
     * System Components (AWS Auto Scaling events)
   
   Example from Netflix:
   ```json
   {
     "event": "VideoStarted",
     "userId": "user123",
     "contentId": "movie789",
     "timestamp": "2024-03-15T10:30:00Z",
     "deviceType": "smart_tv"
   }
   ```

2. **Event Consumers**
   - Definition: Components that listen and react to events
   - Real Examples:
     * Analytics Systems (Google Analytics real-time)
     * Notification Services (Slack's message system)
     * Monitoring Tools (Datadog's alerts)
     * Cache Invalidation (Redis cache updates)
   
   Example from Slack:
   ```json
   {
     "event": "MessageReceived",
     "channelId": "C123456",
     "listen_for": ["new_message", "message_edited"],
     "actions": ["send_notification", "update_badge"]
   }
   ```

3. **Event Broker/Message Bus**
   - Definition: Middleware that manages event delivery
   - Popular Technologies:
     * Apache Kafka (Used by LinkedIn)
     * RabbitMQ (Used by Reddit)
     * Amazon SQS (Used by Airbnb)
     * Google Cloud Pub/Sub (Used by Spotify)
   
   Kafka Example Configuration:
   ```yaml
   topic: order_events
   partitions: 5
   replication-factor: 3
   retention.ms: 604800000  # 7 days
   ```

4. **Event Processors**
   - Definition: Components that handle event logic and transformations
   - Real Examples:
     * Payment Processing (Stripe's payment flow)
     * Order Fulfillment (Amazon's order system)
     * Content Moderation (YouTube's video processing)
   
   Example from YouTube:
   ```python
   def process_video_upload(event):
       video_id = event['video_id']
       # 1. Generate thumbnails
       # 2. Check copyright
       # 3. Convert to different formats
       # 4. Update recommendation engine
   ```

5. **Event Storage**
   - Definition: Systems that persist event data
   - Technologies:
     * Apache Cassandra (Used by Instagram)
     * EventStoreDB (Used by gaming platforms)
     * MongoDB (Used by Uber)
   
   Example Schema:
   ```json
   {
     "event_id": "uuid",
     "event_type": "string",
     "timestamp": "datetime",
     "data": "json",
     "metadata": {
       "version": "string",
       "source": "string"
     }
   }
   ```

### Real Implementation Example: Uber's Trip Management

1. **Trip Request Flow**
   ```mermaid
   graph LR
   A[User App] --> B[Event Producer]
   B --> C[Kafka]
   C --> D[Driver Matching Service]
   C --> E[Pricing Service]
   C --> F[Analytics Service]
   ```

2. **Event Examples**
   ```json
   // Trip Request Event
   {
     "event": "TripRequested",
     "tripId": "trip123",
     "userId": "user456",
     "location": {
       "pickup": {"lat": 37.7749, "lng": -122.4194},
       "destination": {"lat": 37.7833, "lng": -122.4167}
     },
     "timestamp": "2024-03-15T10:30:00Z"
   }

   // Driver Assignment Event
   {
     "event": "DriverAssigned",
     "tripId": "trip123",
     "driverId": "driver789",
     "estimatedArrival": "2024-03-15T10:35:00Z"
   }
   ```

## Vietnamese Version

### Kiến trúc hướng sự kiện là gì?
Kiến trúc hướng sự kiện (EDA) là một mẫu kiến trúc phần mềm trong đó các thành phần giao tiếp thông qua sự kiện. Giống như hệ thống thông báo của mạng xã hội hiện đại - khi điều gì đó xảy ra (một sự kiện), các bên quan tâm được thông báo và có thể phản ứng tương ứng.

### Ví dụ thực tế: Nền tảng thương mại điện tử (Như Tiki)

1. **Khách hàng đặt hàng**
   ```json
   {
     "event": "TaoDonHang",
     "data": {
       "maDonHang": "12345",
       "maKhachHang": "kh789",
       "sanPham": [
         {"maSP": "sp123", "soLuong": 2},
         {"maSP": "sp456", "soLuong": 1}
       ],
       "tongTien": 150000
     }
   }
   ```

2. **Nhiều dịch vụ phản ứng**
   - Dịch vụ thanh toán: Xử lý thanh toán
   - Dịch vụ kho: Cập nhật tồn kho
   - Dịch vụ thông báo: Gửi email xác nhận
   - Dịch vụ phân tích: Cập nhật số liệu bán hàng

### Các thành phần cốt lõi

1. **Nhà sản xuất sự kiện (Event Producers)**
   - Định nghĩa: Thành phần tạo ra và phát ra sự kiện
   - Ví dụ thực tế:
     * Cảm biến IoT (cảm biến xe Tesla)
     * Giao diện người dùng (trình phát video Netflix)
     * API bên ngoài (webhook thanh toán Stripe)
     * Thành phần hệ thống (sự kiện tự động mở rộng AWS)
   
   Ví dụ từ Netflix:
   ```json
   {
     "event": "BatDauVideo",
     "maKhachHang": "kh123",
     "maNoiDung": "phim789",
     "thoiGian": "2024-03-15T10:30:00Z",
     "loaiThietBi": "smart_tv"
   }
   ```

2. **Người tiêu thụ sự kiện (Event Consumers)**
   - Định nghĩa: Thành phần lắng nghe và phản ứng với sự kiện
   - Ví dụ thực tế:
     * Hệ thống phân tích (Google Analytics thời gian thực)
     * Dịch vụ thông báo (hệ thống tin nhắn Slack)
     * Công cụ giám sát (cảnh báo Datadog)
     * Vô hiệu hóa bộ nhớ đệm (cập nhật Redis cache)
   
   Ví dụ từ Slack:
   ```json
   {
     "event": "NhanTinNhan",
     "maKenh": "K123456",
     "langNghe": ["tin_nhan_moi", "tin_nhan_chinh_sua"],
     "hanhDong": ["gui_thong_bao", "cap_nhat_badge"]
   }
   ```

3. **Bộ điều phối sự kiện (Event Broker)**
   - Định nghĩa: Phần mềm trung gian quản lý việc phân phối sự kiện
   - Công nghệ phổ biến:
     * Apache Kafka (LinkedIn sử dụng)
     * RabbitMQ (Reddit sử dụng)
     * Amazon SQS (Airbnb sử dụng)
     * Google Cloud Pub/Sub (Spotify sử dụng)
   
   Ví dụ cấu hình Kafka:
   ```yaml
   topic: su_kien_don_hang
   partitions: 5
   replication-factor: 3
   retention.ms: 604800000  # 7 ngày
   ```

4. **Bộ xử lý sự kiện (Event Processors)**
   - Định nghĩa: Thành phần xử lý logic và chuyển đổi sự kiện
   - Ví dụ thực tế:
     * Xử lý thanh toán (luồng thanh toán Stripe)
     * Xử lý đơn hàng (hệ thống đơn hàng Amazon)
     * Kiểm duyệt nội dung (xử lý video YouTube)
   
   Ví dụ từ YouTube:
   ```python
   def xu_ly_tai_len_video(event):
       ma_video = event['ma_video']
       # 1. Tạo thumbnail
       # 2. Kiểm tra bản quyền
       # 3. Chuyển đổi định dạng
       # 4. Cập nhật công cụ đề xuất
   ```

5. **Lưu trữ sự kiện (Event Storage)**
   - Định nghĩa: Hệ thống lưu trữ dữ liệu sự kiện
   - Công nghệ:
     * Apache Cassandra (Instagram sử dụng)
     * EventStoreDB (nền tảng game sử dụng)
     * MongoDB (Uber sử dụng)
   
   Ví dụ Schema:
   ```json
   {
     "ma_su_kien": "uuid",
     "loai_su_kien": "string",
     "thoi_gian": "datetime",
     "du_lieu": "json",
     "metadata": {
       "phien_ban": "string",
       "nguon": "string"
     }
   }
   ```

### Ví dụ triển khai thực tế: Quản lý chuyến đi của Grab

1. **Luồng yêu cầu chuyến đi**
   ```mermaid
   graph LR
   A[Ứng dụng khách] --> B[Nhà sản xuất sự kiện]
   B --> C[Kafka]
   C --> D[Dịch vụ ghép đôi tài xế]
   C --> E[Dịch vụ tính giá]
   C --> F[Dịch vụ phân tích]
   ```

2. **Ví dụ sự kiện**
   ```json
   // Sự kiện yêu cầu chuyến đi
   {
     "event": "YeuCauChuyenDi",
     "maChuyenDi": "cd123",
     "maKhachHang": "kh456",
     "viTri": {
       "diemDon": {"lat": 10.7769, "lng": 106.7009},
       "diemDen": {"lat": 10.7800, "lng": 106.6900}
     },
     "thoiGian": "2024-03-15T10:30:00Z"
   }

   // Sự kiện phân công tài xế
   {
     "event": "PhanCongTaiXe",
     "maChuyenDi": "cd123",
     "maTaiXe": "tx789",
     "thoiGianUocTinh": "2024-03-15T10:35:00Z"
   }
   ``` 
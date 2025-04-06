# What is Systems Design 📚

## English Version 🇬🇧

### 🔍 What is Systems Design?

Systems Design is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements. It involves translating user requirements into a detailed blueprint that guides the implementation phase. The goal is to create a well-organized and efficient structure that meets the intended purpose while considering factors like scalability, maintainability, and performance.

### 🚀 Why Learn System Design?

1. **Critical for FAANG Interviews** 🎯
   - Consistently tested in top tech company interviews

2. **Essential for Senior Positions** 👔
   - Required expertise for career advancement

3. **Enhances Job Security** 🔒
   - Valued skill that increases employability

4. **Improves Communication** 🗣️
   - Helps articulate complex technical concepts

5. **Better Decision-Making** 🧠
   - Develops systematic problem-solving approach

### 🎯 Objectives of Systems Design

1. **Practicality** 🛠️
   - Target specific audience needs
   
2. **Accuracy** 🎯
   - Fulfill all functional and non-functional requirements
   
3. **Completeness** ✅
   - Meet all user requirements
   
4. **Efficiency** ⚡
   - Optimize resource usage without over or under-utilizing
   
5. **Reliability** 🛡️
   - Create failure-free environment for set periods
   
6. **Optimization** ⏱️
   - Balance time and space constraints
   
7. **Scalability/Flexibility** 📈
   - Adapt to changing user needs over time
   - *Example: GeeksforGeeks' success due to adaptability*

> **Note:** System Design also helps achieve fault tolerance - the ability of software to continue working even when components fail.

### 💪 Advantages of System Design

> **The greatest advantage of system design is inculcating awareness and creativity in full-stack developers via synergic bonding of API protocols gateways, networking and databases.**

1. **Reduces Design Cost** 💰
   - Uses established patterns and reusable components
   
2. **Speeds Development** 🏃‍♂️
   - Leverages frameworks and libraries for faster creation
   
3. **Saves Time in SDLC** ⏰
   - Streamlines processes for quicker time-to-market
   
4. **Increases Developer Efficiency** 💻
   - Provides familiar tools and methodologies
   
5. **Conserves Resources** 🌱
   - Optimizes workflows and minimizes redundant efforts

### 🧩 Components of Systems Design

1. **Load Balancers** ⚖️
   - Distribute traffic across multiple servers
   
2. **Key-Value Stores** 🔑
   - Store data as key-value pairs using distributed hash tables
   
3. **Blob Storage** 📁
   - Store large unstructured data (e.g., YouTube, Netflix)
   
4. **Databases** 💾
   - Organize data for easy access and management
   
5. **Rate Limiters** 🚦
   - Control maximum request handling
   
6. **Monitoring Systems** 📊
   - Track infrastructure performance
   
7. **Distributed Messaging Queues** 📨
   - Facilitate producer-consumer communication
   
8. **Distributed Unique ID Generators** 🔢
   - Create unique identifiers in distributed environments
   
9. **Distributed Search** 🔍
   - Search across multiple data sources
   
10. **Distributed Logging Services** 📝
    - Collect logs across services
    
11. **Distributed Task Schedulers** 📅
    - Manage computational resources across systems

### 🔄 System Design Life Cycle (SDLC)

The System Design Life Cycle outlines the steps for designing and developing systems, ensuring the end product is reliable, scalable, and maintainable.

### 🏛️ System Architecture

System architecture defines how components are depicted in design and deployment. It's the skeleton design showing components, abstraction levels, and other aspects of a software system - essentially the business logic on a single sheet of paper.

#### System Architecture Patterns:

1. **Client-Server Architecture** 🖥️
   - Separates system into clients requesting services and servers providing them
   
2. **Event-Driven Architecture** ⚡
   - Uses events to trigger communication between decoupled components
   
3. **Microkernel Architecture** 🧠
   - Centers around a core system with plugins for additional features
   
4. **Microservices Architecture** 🧩
   - Breaks applications into independent services

### 📦 Modularity and Interfaces

1. **Modularity**
   - Breaks complex products into smaller, independent components
   - Allows separate development and testing
   - Enables changes without affecting the entire system
   
2. **Interfaces**
   - Points where users interact with the system
   - Includes navigation elements, forms, and displays
   - Should be intuitive and user-friendly

### 📈 Evolution/Upgrade/Scaling of Existing Systems

With increasing tech usage, scalable systems are essential to prevent crashes as user numbers grow.

Two scaling options:

1. **Vertical Scaling** ⬆️
   - Upgrade specifications of existing system
   - Improve processor, RAM, disk size
   - Focus on availability rather than scalability
   
2. **Horizontal Scaling** ➡️
   - Create distributed system by connecting multiple systems
   - Add more systems (blocks) to scale up
   - Addresses both availability and scalability

### 🔄 How Data Flows Between Systems

Data Flow Diagrams (DFDs) graphically represent data flow through information systems, showing how a system divides into smaller portions.

#### Components of DFD:
- **Square** 🟥 - Source/destination of data
- **Arrow** ➡️ - Data flow pipeline
- **Circle/Bubble** ⭕ - Process transforming data
- **Open Rectangle** 📂 - Data store/repository

> **Note:** Sender and Receiver should be written in uppercase as per DFD conventions.

### 🛫 System Design Example: Airline Reservation System

A practical example illustrating system design components and considerations through a context-level flow diagram:

- **Data Flow**: Passenger initiates travel request
- **Entity Interaction**: Request transmitted to Travel Agent and Airline
- **Ticketing Process**: Travel Agent issues ticket based on availability
- **Reservation Handling**: System generates reservation request when tickets unavailable

---

## Vietnamese Version 🇻🇳

### 🔍 Systems Design là gì?

Systems Design là quá trình xác định kiến trúc, thành phần, module, giao diện và dữ liệu cho một hệ thống để đáp ứng các yêu cầu cụ thể. Nó liên quan đến việc chuyển đổi yêu cầu người dùng thành bản thiết kế chi tiết hướng dẫn giai đoạn triển khai. Mục tiêu là tạo ra một cấu trúc được tổ chức tốt và hiệu quả đáp ứng mục đích dự định đồng thời xem xét các yếu tố như khả năng mở rộng, khả năng bảo trì và hiệu suất.

### 🚀 Tại sao nên học System Design?

1. **Quan trọng cho phỏng vấn FAANG** 🎯
   - Thường xuyên được kiểm tra trong các cuộc phỏng vấn công ty công nghệ hàng đầu

2. **Cần thiết cho vị trí cấp cao** 👔
   - Yêu cầu chuyên môn để phát triển sự nghiệp

3. **Tăng cường an toàn việc làm** 🔒
   - Kỹ năng có giá trị tăng khả năng tuyển dụng

4. **Cải thiện giao tiếp** 🗣️
   - Giúp diễn đạt các khái niệm kỹ thuật phức tạp

5. **Ra quyết định tốt hơn** 🧠
   - Phát triển cách tiếp cận giải quyết vấn đề có hệ thống

### 🎯 Mục tiêu của Systems Design

1. **Tính thực tiễn** 🛠️
   - Nhắm đến nhu cầu của đối tượng cụ thể
   
2. **Độ chính xác** 🎯
   - Đáp ứng tất cả yêu cầu chức năng và phi chức năng
   
3. **Tính đầy đủ** ✅
   - Đáp ứng tất cả yêu cầu người dùng
   
4. **Hiệu quả** ⚡
   - Tối ưu hóa việc sử dụng tài nguyên mà không quá mức hoặc dưới mức
   
5. **Độ tin cậy** 🛡️
   - Tạo môi trường không lỗi trong thời gian nhất định
   
6. **Tối ưu hóa** ⏱️
   - Cân bằng các ràng buộc về thời gian và không gian
   
7. **Khả năng mở rộng/Linh hoạt** 📈
   - Thích ứng với nhu cầu người dùng thay đổi theo thời gian
   - *Ví dụ: Thành công của GeeksforGeeks nhờ khả năng thích ứng*

> **Lưu ý:** System Design cũng giúp đạt được khả năng chịu lỗi - khả năng phần mềm tiếp tục hoạt động ngay cả khi các thành phần bị lỗi.

### 💪 Lợi ích của System Design

> **Lợi ích lớn nhất của thiết kế hệ thống là nuôi dưỡng nhận thức và sáng tạo ở các nhà phát triển full-stack thông qua liên kết hiệp đồng của các giao thức API, cổng giao tiếp, mạng và cơ sở dữ liệu.**

1. **Giảm chi phí thiết kế** 💰
   - Sử dụng các mẫu thiết lập và thành phần có thể tái sử dụng
   
2. **Tăng tốc phát triển** 🏃‍♂️
   - Tận dụng framework và thư viện để tạo nhanh hơn
   
3. **Tiết kiệm thời gian trong SDLC** ⏰
   - Hợp lý hóa quy trình để đưa ra thị trường nhanh hơn
   
4. **Tăng hiệu quả nhà phát triển** 💻
   - Cung cấp công cụ và phương pháp quen thuộc
   
5. **Bảo tồn tài nguyên** 🌱
   - Tối ưu hóa quy trình làm việc và giảm thiểu nỗ lực trùng lặp

### 🧩 Các thành phần của Systems Design

1. **Bộ cân bằng tải** ⚖️
   - Phân phối lưu lượng truy cập qua nhiều máy chủ
   
2. **Kho lưu trữ Key-Value** 🔑
   - Lưu trữ dữ liệu dưới dạng cặp key-value sử dụng bảng băm phân tán
   
3. **Bộ nhớ Blob** 📁
   - Lưu trữ dữ liệu phi cấu trúc lớn (ví dụ: YouTube, Netflix)
   
4. **Cơ sở dữ liệu** 💾
   - Tổ chức dữ liệu để dễ dàng truy cập và quản lý
   
5. **Bộ giới hạn tốc độ** 🚦
   - Kiểm soát việc xử lý yêu cầu tối đa
   
6. **Hệ thống giám sát** 📊
   - Theo dõi hiệu suất cơ sở hạ tầng
   
7. **Hàng đợi thông điệp phân tán** 📨
   - Tạo điều kiện giao tiếp giữa nhà sản xuất và người tiêu dùng
   
8. **Bộ tạo ID duy nhất phân tán** 🔢
   - Tạo định danh duy nhất trong môi trường phân tán
   
9. **Tìm kiếm phân tán** 🔍
   - Tìm kiếm qua nhiều nguồn dữ liệu
   
10. **Dịch vụ ghi nhật ký phân tán** 📝
    - Thu thập nhật ký qua các dịch vụ
    
11. **Bộ lập lịch tác vụ phân tán** 📅
    - Quản lý tài nguyên tính toán trên các hệ thống

### 🔄 Vòng đời thiết kế hệ thống (SDLC)

Vòng đời thiết kế hệ thống phác thảo các bước để thiết kế và phát triển hệ thống, đảm bảo sản phẩm cuối cùng đáng tin cậy, có thể mở rộng và bảo trì được.

### 🏛️ Kiến trúc hệ thống

Kiến trúc hệ thống xác định cách các thành phần được mô tả trong thiết kế và triển khai. Đó là thiết kế khung xương hiển thị các thành phần, mức độ trừu tượng và các khía cạnh khác của hệ thống phần mềm - về cơ bản là logic kinh doanh trên một tờ giấy.

#### Các mẫu kiến trúc hệ thống:

1. **Kiến trúc Client-Server** 🖥️
   - Tách hệ thống thành khách hàng yêu cầu dịch vụ và máy chủ cung cấp dịch vụ
   
2. **Kiến trúc hướng sự kiện** ⚡
   - Sử dụng sự kiện để kích hoạt giao tiếp giữa các thành phần tách rời
   
3. **Kiến trúc Microkernel** 🧠
   - Tập trung xung quanh hệ thống cốt lõi với plugin cho các tính năng bổ sung
   
4. **Kiến trúc Microservices** 🧩
   - Chia ứng dụng thành các dịch vụ độc lập

### 📦 Tính module hóa và giao diện

1. **Tính module hóa**
   - Chia sản phẩm phức tạp thành các thành phần nhỏ hơn, độc lập
   - Cho phép phát triển và kiểm tra riêng biệt
   - Cho phép thay đổi mà không ảnh hưởng đến toàn bộ hệ thống
   
2. **Giao diện**
   - Điểm người dùng tương tác với hệ thống
   - Bao gồm các phần tử điều hướng, biểu mẫu và hiển thị
   - Nên trực quan và thân thiện với người dùng

### 📈 Phát triển/Nâng cấp/Mở rộng hệ thống hiện có

Với việc sử dụng công nghệ ngày càng tăng, hệ thống có thể mở rộng là cần thiết để ngăn chặn sự cố khi số lượng người dùng tăng lên.

Hai tùy chọn mở rộng:

1. **Mở rộng theo chiều dọc** ⬆️
   - Nâng cấp thông số kỹ thuật của hệ thống hiện có
   - Cải thiện bộ xử lý, RAM, kích thước đĩa
   - Tập trung vào khả năng sẵn có hơn là khả năng mở rộng
   
2. **Mở rộng theo chiều ngang** ➡️
   - Tạo hệ thống phân tán bằng cách kết nối nhiều hệ thống
   - Thêm nhiều hệ thống (khối) để mở rộng
   - Giải quyết cả khả năng sẵn có và khả năng mở rộng

### 🔄 Dữ liệu di chuyển giữa các hệ thống như thế nào

Sơ đồ luồng dữ liệu (DFDs) biểu diễn đồ họa luồng dữ liệu thông qua hệ thống thông tin, cho thấy cách hệ thống chia thành các phần nhỏ hơn.

#### Thành phần của DFD:
- **Hình vuông** 🟥 - Nguồn/đích của dữ liệu
- **Mũi tên** ➡️ - Đường dẫn luồng dữ liệu
- **Hình tròn/Bong bóng** ⭕ - Quá trình chuyển đổi dữ liệu
- **Hình chữ nhật mở** 📂 - Kho lưu trữ dữ liệu

> **Lưu ý:** Người gửi và người nhận nên được viết bằng chữ in hoa theo quy ước DFD.

### 🛫 Ví dụ thiết kế hệ thống: Hệ thống đặt vé máy bay

Một ví dụ thực tế minh họa các thành phần và cách thiết kế hệ thống thông qua sơ đồ luồng cấp ngữ cảnh:

- **Luồng dữ liệu**: Hành khách khởi tạo yêu cầu đi lại
- **Tương tác thực thể**: Yêu cầu được truyền đến Đại lý du lịch và Hãng hàng không
- **Quy trình đặt vé**: Đại lý du lịch cấp vé dựa trên tình trạng còn chỗ
- **Xử lý đặt chỗ**: Hệ thống tạo yêu cầu đặt chỗ khi không còn vé
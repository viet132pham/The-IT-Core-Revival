# Load Balancer in System Design

## What is a Load Balancer?

A load balancer is a crucial component in system design that distributes incoming network traffic across multiple servers. Its main purpose is to ensure that no single server is overburdened with too many requests, which helps improve the performance, reliability, and availability of applications. This is particularly important for high-traffic websites, applications, or services that need to handle numerous simultaneous user requests without experiencing slowdowns or outages.

Load balancers sit between client devices and backend servers, receiving all incoming requests before distributing them across the server pool according to predefined algorithms and rules.

![How-Load-Balancer-works](https://media.geeksforgeeks.org/wp-content/uploads/20221219163237/How-Load-Balancer-works.png)

## How Load Balancer Works?

Let's see how a load balancer works in simple steps:

1. **Receives Incoming Requests**: When users try to access a website or application, their requests first go to the load balancer instead of directly to a server.

2. **Checks Server Health**: The load balancer continuously monitors the status of all servers. It checks which servers are healthy and ready to handle requests.

3. **Distributes Traffic**: Based on factors like server load, response time, or proximity, the load balancer forwards each request to the most appropriate server. This helps avoid any server getting overloaded.

4. **Handles Server Failures**: If a server goes down or becomes unresponsive, the load balancer automatically stops sending traffic to that server and redirects it to others that are still functioning properly.

5. **Optimizes Performance**: By spreading traffic efficiently and using healthy servers, load balancers improve overall performance and reduce delays.

## Types of Load Balancers

### 1. Hardware Load Balancers

Hardware load balancers are physical devices specifically designed to distribute network traffic. They often include specialized processors and optimized components for handling high volumes of traffic.

**Advantages**:
- High performance and reliability
- Dedicated hardware for load balancing tasks
- Often include advanced features and security capabilities

**Disadvantages**:
- Expensive to purchase and maintain
- Limited scalability (requires purchasing additional hardware)
- Physical installation and maintenance required

### 2. Software Load Balancers

Software load balancers are applications that run on standard operating systems and general-purpose hardware. They perform the same functions as hardware load balancers but through software implementation.

**Advantages**:
- Cost-effective compared to hardware solutions
- Flexible deployment options
- Easier to scale by adding more software instances
- Can be customized to specific requirements

**Disadvantages**:
- May have performance limitations compared to hardware solutions
- Requires management of the underlying operating system

### 3. Cloud Load Balancers

Cloud load balancers, which are offered as a service by cloud providers like AWS, Google Cloud, and Azure, automatically distribute traffic without requiring physical hardware. Users just pay for the resources they use, and they are very scalable.

**Advantages**:
- Pay-as-you-go pricing model
- No hardware to maintain
- Easily scalable to handle traffic spikes
- Integrated with other cloud services

**Disadvantages**:
- Potential vendor lock-in
- Less control over the infrastructure
- Ongoing costs that may grow with usage

### 4. Layer 4 (Transport Layer) Load Balancers

Layer 4 load balancers operate at the transport layer of the OSI model and use IP addresses and port numbers (TCP/UDP) to distribute traffic. They do not examine the actual content of the packets being transmitted.

**Advantages**:
- Faster processing due to simpler routing decisions
- Lower overhead and higher throughput
- Better performance for high-volume traffic

**Disadvantages**:
- Limited visibility into application-specific details
- Cannot make routing decisions based on content

### 5. Layer 7 (Application Layer) Load Balancers

Layer 7 load balancers operate at the application layer and can examine the content of requests, including HTTP headers, URLs, and cookies. This allows for more sophisticated routing decisions.

**Advantages**:
- Greater control over traffic routing based on content
- Can implement application-specific optimizations
- Support for content-based routing and SSL termination

**Disadvantages**:
- Higher processing overhead
- Can be more complex to configure and manage
- Generally slower than Layer 4 load balancers

## Load Balancing Algorithms

Load balancers use various algorithms to determine how to distribute incoming requests among the available servers. Here are some common algorithms:

### 1. Round Robin

The round robin algorithm distributes requests sequentially to each server in the pool. The first request goes to server 1, the second to server 2, and so on, cycling back to the first server once all servers have been used.

**Best for**: Simple implementations where servers have similar specifications and workloads.

### 2. Least Connection

The least connection algorithm directs traffic to the server with the fewest active connections. This approach is based on the assumption that a server with fewer active connections will be able to process new requests more quickly.

**Best for**: Environments where requests may take varied amounts of time to process.

### 3. Weighted Round Robin

Similar to round robin, but servers are assigned different weights based on their capabilities. Servers with higher weights receive more requests proportionally to their capacity.

**Best for**: Environments with servers of varying capabilities or when some servers should handle more traffic than others.

### 4. IP Hash

This algorithm uses the client's IP address to determine which server should receive the request. The IP address is hashed to produce a value that maps to a specific server, ensuring that the same client always reaches the same server.

**Best for**: Applications that require session persistence or where client state needs to be maintained on a specific server.

### 5. Least Response Time

This algorithm selects the server with the lowest combination of fewer active connections and faster response time, ensuring both low latency and balanced distribution.

**Best for**: Performance-critical applications where minimizing response time is essential.

## Benefits of using a Load Balancer

### 1. Increases Performance

Any web server when given huge traffic may not perform well and can give down time to users, thereby degrading the performance. However, a load balancer ensures users experience no down time and get better performance.

### 2. Increased Scalability

As the business grows, more users will access the application which means more traffic. Using a load balancer makes it easy to scale horizontally by adding more servers to the pool without disrupting service.

### 3. Redundancy and High Availability

Applications' reliability and availability are improved by load balancers, which divide traffic among multiple servers. If one server fails, the load balancer reroutes traffic to servers that are in good condition, preventing service interruptions.

### 4. Health Monitoring

Load balancers continuously monitor the health of servers, directing traffic away from servers experiencing issues or downtime. This proactive approach helps maintain service quality.

### 5. SSL Termination

Some load balancers can handle SSL/TLS encryption and decryption, offloading this resource-intensive task from application servers. This improves overall system performance by freeing application servers to focus on their primary tasks.

### 6. Flexibility in Maintenance

With a load balancer in place, individual servers can be taken offline for maintenance or updates without affecting the overall service. The load balancer simply stops routing traffic to the server being maintained.

## Dynamic vs Static Load Balancing

### Static Load Balancing

Static load balancing distributes workloads based on predetermined rules without considering the current state of the system. The distribution plan is established at the beginning and remains fixed.

**Characteristics**:
- Rules are set in advance and don't change
- Does not adapt to changing server conditions
- Simpler to implement
- Works well in environments with predictable workloads

### Dynamic Load Balancing

Dynamic load balancing makes real-time decisions regarding the distribution of incoming network traffic based on the current state of the servers. This method adapts to changing conditions in the system, including resource availability, network traffic, and server load.

**Characteristics**:
- Adapts to changing server conditions
- Monitors server health and performance
- Makes decisions based on current data
- Better suited for unpredictable or variable workloads
- More complex to implement

**Types of Dynamic Load Balancing Algorithms**:
1. **Least Connection Method**: Directs traffic to the server with the fewest active connections
2. **Least Response Time Method**: Selects the server with the fastest response time and fewest connections

## Real-world Examples of Load Balancing

1. **Content Delivery Networks (CDNs)**: CDNs like Cloudflare and Akamai use load balancing to direct users to the closest server containing requested content.

2. **E-commerce Platforms**: During high-traffic events like Black Friday, e-commerce sites use load balancers to distribute customer requests across multiple servers to handle sudden traffic spikes.

3. **Social Media Platforms**: Sites like Facebook and Twitter use sophisticated load balancing to manage millions of simultaneous user interactions.

4. **Video Streaming Services**: Platforms like Netflix and YouTube use load balancing to ensure smooth content delivery to millions of users watching different videos simultaneously.

5. **Cloud Services**: AWS Elastic Load Balancer, Google Cloud Load Balancing, and Azure Load Balancer provide load balancing as a service to applications hosted on their platforms.

## Load Balancer vs. Reverse Proxy

While load balancers and reverse proxies share some similarities, they serve different primary purposes:

### Load Balancer
- **Primary Purpose**: Distribute client requests across multiple servers to balance load
- **Focus**: Scalability and availability
- **Traffic Direction**: One-to-many (client to multiple servers)

### Reverse Proxy
- **Primary Purpose**: Act as an intermediary between clients and servers, often for security reasons
- **Focus**: Security, caching, and privacy
- **Traffic Direction**: Many-to-one (multiple clients to server/application)

Many modern tools combine both functionalities, with products like NGINX and HAProxy able to function as both load balancers and reverse proxies.

## Conclusion

Load balancers are essential components in modern system design, particularly for applications that need to handle high traffic volumes or require high availability. By distributing workloads across multiple servers, load balancers help prevent any single server from becoming overwhelmed, ensuring better performance and reliability for end users. With various types and algorithms available, organizations can choose load balancing solutions that best fit their specific requirements and infrastructure.

---

# Bộ cân bằng tải trong Thiết kế Hệ thống

## Bộ cân bằng tải là gì?

Bộ cân bằng tải là một thành phần quan trọng trong thiết kế hệ thống, có nhiệm vụ phân phối lưu lượng mạng đến giữa nhiều máy chủ. Mục đích chính của nó là đảm bảo không có máy chủ nào bị quá tải với quá nhiều yêu cầu, giúp cải thiện hiệu suất, độ tin cậy và tính khả dụng của ứng dụng. Điều này đặc biệt quan trọng đối với các trang web, ứng dụng hoặc dịch vụ có lưu lượng truy cập cao cần xử lý nhiều yêu cầu đồng thời từ người dùng mà không bị chậm hoặc gián đoạn.

Bộ cân bằng tải nằm giữa các thiết bị của khách hàng và máy chủ backend, nhận tất cả các yêu cầu đến trước khi phân phối chúng trên nhóm máy chủ theo các thuật toán và quy tắc được xác định trước.

![How-Load-Balancer-works](https://media.geeksforgeeks.org/wp-content/uploads/20221219163237/How-Load-Balancer-works.png)

## Cách thức hoạt động của Bộ cân bằng tải?

Hãy xem cách bộ cân bằng tải hoạt động qua các bước đơn giản:

1. **Nhận yêu cầu đến**: Khi người dùng truy cập vào một trang web hoặc ứng dụng, yêu cầu của họ sẽ đi đến bộ cân bằng tải trước thay vì trực tiếp đến một máy chủ.

2. **Kiểm tra sức khỏe máy chủ**: Bộ cân bằng tải liên tục giám sát trạng thái của tất cả các máy chủ. Nó kiểm tra xem máy chủ nào khỏe mạnh và sẵn sàng xử lý yêu cầu.

3. **Phân phối lưu lượng**: Dựa trên các yếu tố như tải máy chủ, thời gian phản hồi, hoặc vị trí địa lý, bộ cân bằng tải chuyển tiếp mỗi yêu cầu đến máy chủ phù hợp nhất. Điều này giúp tránh máy chủ nào đó bị quá tải.

4. **Xử lý lỗi máy chủ**: Nếu một máy chủ ngừng hoạt động hoặc không phản hồi, bộ cân bằng tải tự động ngừng gửi lưu lượng đến máy chủ đó và chuyển hướng đến các máy chủ khác vẫn đang hoạt động bình thường.

5. **Tối ưu hóa hiệu suất**: Bằng cách phân phối lưu lượng hiệu quả và sử dụng các máy chủ khỏe mạnh, bộ cân bằng tải cải thiện hiệu suất tổng thể và giảm độ trễ.

## Các loại Bộ cân bằng tải

### 1. Bộ cân bằng tải phần cứng

Bộ cân bằng tải phần cứng là các thiết bị vật lý được thiết kế đặc biệt để phân phối lưu lượng mạng. Chúng thường bao gồm các bộ xử lý chuyên dụng và các thành phần được tối ưu hóa để xử lý khối lượng lưu lượng cao.

**Ưu điểm**:
- Hiệu suất và độ tin cậy cao
- Phần cứng chuyên dụng cho các tác vụ cân bằng tải
- Thường bao gồm các tính năng nâng cao và khả năng bảo mật

**Nhược điểm**:
- Chi phí mua và bảo trì cao
- Khả năng mở rộng hạn chế (yêu cầu mua thêm phần cứng)
- Yêu cầu lắp đặt và bảo trì vật lý

### 2. Bộ cân bằng tải phần mềm

Bộ cân bằng tải phần mềm là các ứng dụng chạy trên hệ điều hành tiêu chuẩn và phần cứng đa năng. Chúng thực hiện các chức năng giống như bộ cân bằng tải phần cứng nhưng thông qua việc triển khai phần mềm.

**Ưu điểm**:
- Tiết kiệm chi phí so với giải pháp phần cứng
- Tùy chọn triển khai linh hoạt
- Dễ dàng mở rộng bằng cách thêm nhiều phiên bản phần mềm
- Có thể tùy chỉnh theo yêu cầu cụ thể

**Nhược điểm**:
- Có thể có giới hạn về hiệu suất so với giải pháp phần cứng
- Yêu cầu quản lý hệ điều hành cơ bản

### 3. Bộ cân bằng tải đám mây

Bộ cân bằng tải đám mây, được cung cấp như một dịch vụ bởi các nhà cung cấp đám mây như AWS, Google Cloud và Azure, tự động phân phối lưu lượng mà không cần phần cứng vật lý. Người dùng chỉ trả tiền cho tài nguyên họ sử dụng, và chúng rất có khả năng mở rộng.

**Ưu điểm**:
- Mô hình thanh toán theo sử dụng
- Không có phần cứng để bảo trì
- Dễ dàng mở rộng để xử lý đột biến lưu lượng
- Tích hợp với các dịch vụ đám mây khác

**Nhược điểm**:
- Tiềm ẩn khóa chặt với nhà cung cấp
- Ít kiểm soát hơn đối với cơ sở hạ tầng
- Chi phí liên tục có thể tăng theo mức sử dụng

### 4. Bộ cân bằng tải Lớp 4 (Tầng vận chuyển)

Bộ cân bằng tải Lớp 4 hoạt động ở tầng vận chuyển của mô hình OSI và sử dụng địa chỉ IP và số cổng (TCP/UDP) để phân phối lưu lượng. Chúng không kiểm tra nội dung thực của các gói tin đang được truyền.

**Ưu điểm**:
- Xử lý nhanh hơn do quyết định định tuyến đơn giản
- Ít tải và thông lượng cao hơn
- Hiệu suất tốt hơn cho lưu lượng khối lượng lớn

**Nhược điểm**:
- Khả năng hiển thị hạn chế vào chi tiết ứng dụng cụ thể
- Không thể đưa ra quyết định định tuyến dựa trên nội dung

### 5. Bộ cân bằng tải Lớp 7 (Tầng ứng dụng)

Bộ cân bằng tải Lớp 7 hoạt động ở tầng ứng dụng và có thể kiểm tra nội dung của yêu cầu, bao gồm tiêu đề HTTP, URL và cookie. Điều này cho phép các quyết định định tuyến phức tạp hơn.

**Ưu điểm**:
- Kiểm soát tốt hơn việc định tuyến lưu lượng dựa trên nội dung
- Có thể thực hiện tối ưu hóa cụ thể cho ứng dụng
- Hỗ trợ định tuyến dựa trên nội dung và chấm dứt SSL

**Nhược điểm**:
- Tải xử lý cao hơn
- Có thể phức tạp hơn để cấu hình và quản lý
- Thường chậm hơn bộ cân bằng tải Lớp 4

## Thuật toán Cân bằng tải

Bộ cân bằng tải sử dụng nhiều thuật toán khác nhau để xác định cách phân phối các yêu cầu đến trong số các máy chủ khả dụng. Dưới đây là một số thuật toán phổ biến:

### 1. Round Robin

Thuật toán Round Robin phân phối yêu cầu tuần tự cho mỗi máy chủ trong nhóm. Yêu cầu đầu tiên đến máy chủ 1, yêu cầu thứ hai đến máy chủ 2, và tiếp tục, quay trở lại máy chủ đầu tiên khi tất cả các máy chủ đã được sử dụng.

**Tốt nhất cho**: Triển khai đơn giản nơi các máy chủ có thông số kỹ thuật và khối lượng công việc tương tự.

### 2. Kết nối ít nhất

Thuật toán kết nối ít nhất chuyển hướng lưu lượng đến máy chủ có ít kết nối hoạt động nhất. Cách tiếp cận này dựa trên giả định rằng máy chủ với ít kết nối hoạt động hơn sẽ có thể xử lý yêu cầu mới nhanh hơn.

**Tốt nhất cho**: Môi trường mà các yêu cầu có thể mất lượng thời gian khác nhau để xử lý.

### 3. Weighted Round Robin

Tương tự như Round Robin, nhưng các máy chủ được gán các trọng số khác nhau dựa trên khả năng của chúng. Các máy chủ có trọng số cao hơn sẽ nhận nhiều yêu cầu hơn tỷ lệ thuận với dung lượng của chúng.

**Tốt nhất cho**: Môi trường với máy chủ có khả năng khác nhau hoặc khi một số máy chủ nên xử lý nhiều lưu lượng hơn các máy chủ khác.

### 4. Băm IP

Thuật toán này sử dụng địa chỉ IP của khách hàng để xác định máy chủ nào sẽ nhận yêu cầu. Địa chỉ IP được băm để tạo ra một giá trị ánh xạ đến một máy chủ cụ thể, đảm bảo rằng cùng một khách hàng luôn đến cùng một máy chủ.

**Tốt nhất cho**: Ứng dụng yêu cầu duy trì phiên hoặc nơi trạng thái của khách hàng cần được duy trì trên một máy chủ cụ thể.

### 5. Thời gian phản hồi ít nhất

Thuật toán này chọn máy chủ có sự kết hợp thấp nhất của ít kết nối hoạt động hơn và thời gian phản hồi nhanh hơn, đảm bảo cả độ trễ thấp và phân phối cân bằng.

**Tốt nhất cho**: Ứng dụng quan trọng về hiệu suất nơi việc giảm thiểu thời gian phản hồi là cần thiết.

## Lợi ích của việc sử dụng Bộ cân bằng tải

### 1. Tăng hiệu suất

Bất kỳ máy chủ web nào khi nhận được lưu lượng lớn đều có thể hoạt động không tốt và có thể gây thời gian chết cho người dùng, do đó làm giảm hiệu suất. Tuy nhiên, một bộ cân bằng tải đảm bảo người dùng không gặp thời gian chết và có hiệu suất tốt hơn.

### 2. Tăng khả năng mở rộng

Khi doanh nghiệp phát triển, sẽ có nhiều người dùng truy cập ứng dụng hơn, nghĩa là nhiều lưu lượng hơn. Sử dụng bộ cân bằng tải giúp dễ dàng mở rộng theo chiều ngang bằng cách thêm nhiều máy chủ vào nhóm mà không làm gián đoạn dịch vụ.

### 3. Dự phòng và tính khả dụng cao

Độ tin cậy và tính khả dụng của ứng dụng được cải thiện bởi các bộ cân bằng tải, phân chia lưu lượng giữa nhiều máy chủ. Nếu một máy chủ gặp sự cố, bộ cân bằng tải chuyển hướng lưu lượng đến các máy chủ đang trong tình trạng tốt, ngăn chặn gián đoạn dịch vụ.

### 4. Giám sát sức khỏe

Bộ cân bằng tải liên tục giám sát sức khỏe của các máy chủ, chuyển hướng lưu lượng khỏi các máy chủ gặp sự cố hoặc thời gian chết. Cách tiếp cận chủ động này giúp duy trì chất lượng dịch vụ.

### 5. Chấm dứt SSL

Một số bộ cân bằng tải có thể xử lý mã hóa và giải mã SSL/TLS, giảm tải công việc đòi hỏi nhiều tài nguyên này khỏi các máy chủ ứng dụng. Điều này cải thiện hiệu suất hệ thống tổng thể bằng cách giải phóng các máy chủ ứng dụng để tập trung vào các nhiệm vụ chính của chúng.

### 6. Linh hoạt trong bảo trì

Với một bộ cân bằng tải được thiết lập, các máy chủ riêng lẻ có thể được đưa ngoại tuyến để bảo trì hoặc cập nhật mà không ảnh hưởng đến dịch vụ tổng thể. Bộ cân bằng tải đơn giản là ngừng định tuyến lưu lượng đến máy chủ đang được bảo trì.

## Cân bằng tải động và Cân bằng tải tĩnh

### Cân bằng tải tĩnh

Cân bằng tải tĩnh phân phối khối lượng công việc dựa trên các quy tắc được xác định trước mà không xem xét trạng thái hiện tại của hệ thống. Kế hoạch phân phối được thiết lập ngay từ đầu và giữ nguyên.

**Đặc điểm**:
- Quy tắc được thiết lập trước và không thay đổi
- Không thích nghi với điều kiện máy chủ thay đổi
- Đơn giản hơn để triển khai
- Hoạt động tốt trong môi trường với khối lượng công việc có thể dự đoán

### Cân bằng tải động

Cân bằng tải động đưa ra quyết định thời gian thực về việc phân phối lưu lượng mạng đến dựa trên trạng thái hiện tại của các máy chủ. Phương pháp này thích ứng với các điều kiện thay đổi trong hệ thống, bao gồm tính khả dụng của tài nguyên, lưu lượng mạng và tải máy chủ.

**Đặc điểm**:
- Thích nghi với điều kiện máy chủ thay đổi
- Giám sát sức khỏe và hiệu suất máy chủ
- Đưa ra quyết định dựa trên dữ liệu hiện tại
- Phù hợp hơn cho khối lượng công việc không thể dự đoán hoặc biến đổi
- Phức tạp hơn để triển khai

**Các loại thuật toán cân bằng tải động**:
1. **Phương pháp kết nối ít nhất**: Chuyển hướng lưu lượng đến máy chủ có ít kết nối hoạt động nhất
2. **Phương pháp thời gian phản hồi ít nhất**: Chọn máy chủ có thời gian phản hồi nhanh nhất và ít kết nối nhất

## Ví dụ thực tế về Cân bằng tải

1. **Mạng phân phối nội dung (CDNs)**: CDN như Cloudflare và Akamai sử dụng cân bằng tải để chuyển hướng người dùng đến máy chủ gần nhất chứa nội dung được yêu cầu.

2. **Nền tảng thương mại điện tử**: Trong các sự kiện lưu lượng cao như Black Friday, các trang thương mại điện tử sử dụng bộ cân bằng tải để phân phối yêu cầu khách hàng trên nhiều máy chủ để xử lý đột biến lưu lượng đột ngột.

3. **Nền tảng truyền thông xã hội**: Các trang như Facebook và Twitter sử dụng cân bằng tải phức tạp để quản lý hàng triệu tương tác người dùng đồng thời.

4. **Dịch vụ phát trực tuyến video**: Các nền tảng như Netflix và YouTube sử dụng cân bằng tải để đảm bảo cung cấp nội dung mượt mà cho hàng triệu người dùng xem các video khác nhau cùng một lúc.

5. **Dịch vụ đám mây**: AWS Elastic Load Balancer, Google Cloud Load Balancing và Azure Load Balancer cung cấp cân bằng tải như một dịch vụ cho các ứng dụng được lưu trữ trên nền tảng của họ.

## Bộ cân bằng tải và Proxy ngược

Mặc dù bộ cân bằng tải và proxy ngược có một số điểm tương đồng, chúng phục vụ các mục đích chính khác nhau:

### Bộ cân bằng tải
- **Mục đích chính**: Phân phối yêu cầu khách hàng trên nhiều máy chủ để cân bằng tải
- **Trọng tâm**: Khả năng mở rộng và tính khả dụng
- **Hướng lưu lượng**: Một-đến-nhiều (khách hàng đến nhiều máy chủ)

### Proxy ngược
- **Mục đích chính**: Đóng vai trò trung gian giữa khách hàng và máy chủ, thường vì lý do bảo mật
- **Trọng tâm**: Bảo mật, bộ nhớ đệm và quyền riêng tư
- **Hướng lưu lượng**: Nhiều-đến-một (nhiều khách hàng đến máy chủ/ứng dụng)

Nhiều công cụ hiện đại kết hợp cả hai chức năng, với các sản phẩm như NGINX và HAProxy có thể hoạt động như cả bộ cân bằng tải và proxy ngược.

## Kết luận

Bộ cân bằng tải là các thành phần thiết yếu trong thiết kế hệ thống hiện đại, đặc biệt là cho các ứng dụng cần xử lý khối lượng lưu lượng cao hoặc yêu cầu tính khả dụng cao. Bằng cách phân phối khối lượng công việc trên nhiều máy chủ, bộ cân bằng tải giúp ngăn chặn bất kỳ máy chủ đơn lẻ nào bị quá tải, đảm bảo hiệu suất và độ tin cậy tốt hơn cho người dùng cuối. Với nhiều loại và thuật toán khác nhau có sẵn, các tổ chức có thể chọn giải pháp cân bằng tải phù hợp nhất với yêu cầu và cơ sở hạ tầng cụ thể của họ.
# What are the Components of System Design?
*Last Updated: November 18, 2024*

The process of specifying a computer system's architecture, components, modules, interfaces, and data is known as system design. It involves looking at the system's requirements, determining its assumptions and limitations, and defining its high-level structure and components. The primary elements of system design, including databases, load balancers, and messaging systems, will be discussed in this article. Understanding these components helps the development of scalable, effective, and secure systems.

## Table of Contents
1. [Load Balancer](#1-load-balancer)
2. [Caching](#2-caching)
3. [Content Delivery Network (CDN)](#3-content-delivery-network-cdn)
4. [API Gateways](#4-api-gateways)
5. [Key-value Stores](#5-key-value-stores)
6. [Blob Storage & Databases](#6-blob-storage--databases)
7. [Rate Limiters](#7-rate-limiters)
8. [Monitoring System](#8-monitoring-system)
9. [Distributed System Messaging Queue](#9-distributed-system-messaging-queue)
10. [Distributed Unique ID Generator](#10-distributed-unique-id-generator)
11. [Distributed Search](#11-distributed-search)
12. [Distributed Logging Services](#12-distributed-logging-services)
13. [Distributed Task Scheduler](#13-distributed-task-scheduler)

## 1. Load Balancer
A load balancer is a component of system design that divides incoming requests or workloads across several distinct resources or servers. This is useful when a system has many servers and needs to divide requests evenly among them, or when a system receives a large number of requests and wants to split them up across multiple servers to prevent overloading any one of them.

Some common types of load balancers include:

- **Layer 4 load balancers**: Functions at the OSI model's network layer, allocating requests according to their port numbers and source and destination IP addresses.
- **Layer 7 load balancers**: Functions at the OSI model's application layer, distributing requests according to their content, including the URL or HTTP method type.
- **Global load balancers**: Used in distributed systems to distribute requests among multiple servers located in different geographic regions.
- **Application load balancers**: Specialized load balancers designed to work with specific types of applications or protocols, such as HTTP or HTTPS.

## 2. Caching
Caching is a technique for temporarily storing frequently requested data that speeds up its retrieval when needed again. When caching is included in system architecture, the main database or data source is less burdened, which enhances performance and efficiency.

Here's how caching works and why it's beneficial:

- **Quick Access**: When data is cached, it's stored in a faster, temporary storage (like memory) instead of being fetched repeatedly from a slower storage source. This makes retrieving information faster.
- **Reduces Database Load**: The system can process more requests without experiencing any lag by keeping frequently used or popular data in the cache instead of constantly querying the main database.
- **Improves User Experience**: Faster data access means faster response times for users, which improves the overall experience on websites or apps.

## 3. Content Delivery Network (CDN)
A Content Delivery Network (CDN) is a network of servers spread across different regions that enables faster delivery of content to users, such as webpages, movies, and photos. A CDN is utilized in most system designs to increase the speed and dependability of content delivery to consumers, particularly when they are dispersed across many geographical locations.

**How a CDN works**: When a user requests content (like a video or an image), instead of retrieving it from the main server, the request is handled by a nearby CDN server, which has a cached copy of the content. This reduces the distance the data has to travel, making it load faster for the user.

## 4. API Gateways
An API Gateway is like a central doorway or "traffic controller" for requests coming into a system. In system design, it acts as a single entry point for clients (such as apps or websites) to access multiple backend services in an organized and secure way.

Let's see how it works:

- **Request Routing**: A client submits a request to the API Gateway when it wants information or actions from several services. After forwarding the request to the appropriate services, the gateway compiles their answers and provides the client with a single, unified response.
- **Simplifies Client Interaction**: Without an API Gateway, clients might need to connect directly to each service individually, which can be complex. The API Gateway simplifies this by hiding the backend details from clients.
- **Security and Monitoring**: The gateway can handle security features like authentication (checking user identities) and authorization (checking what they're allowed to do). It also helps monitor traffic, so you can track and log usage, spot issues, or prevent attacks.
- **Load Management**: In busy systems, the gateway can help balance and control the flow of requests to prevent overload, ensuring smoother performance.

## 5. Key-value Stores
A key-value store is a type of NoSQL database that is designed for storing data as a collection of key-value pairs. Every piece of data is kept in a key-value store under a distinct key, and the data itself serves as the value. Since key-value stores allow for quick access to data by key, they are typically used to store data that is accessed frequently.

Key-value stores come in various forms, such as:
- **In-memory key-value stores**: Store data in memory for quick access.
- **Persistent key-value stores**: Store data on disk or in a distributed file system for durability.

Key-value stores are generally simpler to use and more scalable than other types of databases, such as RDBMS. However, they are not as well-suited for storing complex structured data that requires advanced querying capabilities.

## 6. Blob Storage & Databases
Blob storage and database systems are two different types of storage systems that can be used to store and manage data.

**Blob storage** (also referred to as object storage) can store large volumes of unstructured data, including documents, photos, videos, and audio files. In general, blob storage systems are very scalable and capable of managing several requests at once. They are widely used to store frequently accessible material, such as user-generated content or media files.

**Database systems**, on the other hand, are designed to hold structured data that has been arranged in a particular manner. RDBMSs, NoSQL databases, and in-memory databases are among the several kinds of database systems. Database systems are typically used to store data that needs to be queried and accessed in a structured way, such as customer records or financial transactions.

## 7. Rate Limiters
Rate limiters are system design components used to restrict the rate at which a system or application responds to requests or carries out specific tasks. This can be helpful in a variety of situations, such as when a system has to guard against receiving too many requests or when a company wants to stop a particular user or group of users from submitting excessive requests that can affect the system's performance.

Some common types of rate limiters include:

- **Request rate limiters**: Used to limit the number of requests that a system or application processes within a given time period.
- **User rate limiters**: Used to limit the rate at which a specific user or group of users can make requests to a system or application.
- **Token bucket rate limiters**: Used to limit the rate at which requests are processed by a system by allowing a certain number of requests to be processed in each time period, with any excess requests being held in a "bucket" until the next time period.

## 8. Monitoring System
A monitoring system is a system design component that is used to collect, analyze, and report on various metrics and performance data related to a system or application. This can be useful in a number of different scenarios, such as when a system needs to track its own performance and availability, or when an organization needs to monitor the performance of its systems and applications to ensure that they are meeting their desired service levels.

Some common types of monitoring systems include:

- **Network monitoring systems**: Used to monitor the performance of a network and its various components, such as routers, switches, and servers.
- **System monitoring systems**: Used to monitor the performance of a computer system and its various components, such as the CPU, memory, and disk usage.
- **Application monitoring systems**: Used to monitor the performance of specific applications or services, such as web servers or databases.

## 9. Distributed System Messaging Queue
A distributed system messaging queue is a system that enables the exchange of messages between different nodes in a distributed system. Messaging queues allow nodes to communicate asynchronously, decoupling the sender and receiver of a message and enabling each node to operate independently.

There are several different types of messaging queues, including:

- **Point-to-point queues**: In this type of queue, messages are delivered to a specific recipient.
- **Publish-subscribe queues**: In this type of queue, messages are published to a topic and are delivered to all subscribers to that topic.
- **Hybrid queues**: Hybrid queues combine elements of both point-to-point and publish-subscribe queues, allowing messages to be delivered to specific recipients or to all subscribers to a topic.

Distributed system messaging queues can be used to enable communication between different components of a distributed system, such as microservices or distributed applications. They can also be used to decouple different parts of the system, allowing each component to operate independently and improving the system's resilience and scalability.

## 10. Distributed Unique ID Generator
A distributed unique ID generator is a system that generates unique identifiers (IDs) that can be used to identify objects or entities in a distributed system. These IDs are typically used to uniquely identify items in a database or to provide a stable identifier for a resource that is accessed over the network.

There are several approaches to generating distributed unique IDs:

- Using a centralized service
- Using a distributed consensus algorithm
- Using timestamps

## 11. Distributed Search
Distributed search refers to the practice of using multiple nodes or servers to index and search large datasets in a distributed system. Distributed search can be used to improve the performance and scalability of search operations, as it allows for parallel processing of search queries and the distribution of data across multiple nodes.

There are several approaches to implementing distributed search, including:

- **Using a distributed search engine**: A distributed search engine is a search platform that is designed to scale horizontally across multiple nodes. These systems typically use a distributed index to store the data being searched, allowing for parallel processing of search queries.
- **Using a database with search capabilities**: Some databases, such as MongoDB and Cassandra, have built-in search capabilities that allow for the indexing and searching of data stored in the database.
- **Using a cloud-based search service**: Cloud-based search services, such as Amazon Elasticsearch Service and Google Cloud Search, can be used to implement distributed search in a distributed system. These services are typically highly scalable and fault-tolerant.

## 12. Distributed Logging Services
Distributed logging refers to the practice of collecting, storing, and analyzing log data from multiple sources in a distributed system. This can be useful for tracking the health and performance of a distributed system, as well as for debugging issues that may arise.

There are several approaches to implementing distributed logging, including:

- Using a centralized logging service
- Using a distributed logging system
- Using a cloud-based logging service

## 13. Distributed Task Scheduler
A distributed task scheduler is a system that is responsible for scheduling and executing tasks in a distributed system. A task scheduler can be used to automate the execution of tasks at regular intervals, on a specific schedule, or in response to certain events.

There are several approaches to implementing a distributed task scheduler, including:

- **Using a standalone task scheduler**: A separate system that is responsible for scheduling and executing tasks in a distributed system. This approach can be simple to implement and allows for flexibility in terms of the types of tasks that can be scheduled.
- **Using a built-in task scheduler**: Some distributed systems, such as container orchestration platforms or cloud-based serverless platforms, have built-in task schedulers that can be used to schedule tasks within the system.
- **Using a cloud-based task scheduler**: Cloud-based task schedulers, such as Amazon Simple Notification Service (SNS) or Google Cloud Scheduler, can be used to schedule tasks in a distributed system.

It is important to choose a distributed task scheduler that meets the specific requirements of the system, taking into account factors such as scalability, performance, and cost.


# Các Thành Phần của Thiết Kế Hệ Thống là gì?
*Cập nhật lần cuối: Ngày 18 tháng 11, 2024*

Thiết kế hệ thống là quá trình xác định kiến trúc, thành phần, mô-đun, giao diện và dữ liệu của một hệ thống máy tính. Quá trình này bao gồm việc xem xét các yêu cầu của hệ thống, xác định các giả định và giới hạn của nó, cũng như định nghĩa cấu trúc và các thành phần cấp cao của hệ thống. Bài viết này sẽ thảo luận về các yếu tố chính của thiết kế hệ thống, bao gồm cơ sở dữ liệu, bộ cân bằng tải và hệ thống nhắn tin. Hiểu về các thành phần này giúp phát triển các hệ thống có khả năng mở rộng, hiệu quả và an toàn.

## Mục Lục
1. [Bộ Cân Bằng Tải](#1-bộ-cân-bằng-tải)
2. [Bộ Nhớ Đệm](#2-bộ-nhớ-đệm)
3. [Mạng Phân Phối Nội Dung (CDN)](#3-mạng-phân-phối-nội-dung-cdn)
4. [Cổng API](#4-cổng-api)
5. [Kho Lưu Trữ Khóa-Giá Trị](#5-kho-lưu-trữ-khóa-giá-trị)
6. [Lưu Trữ Blob & Cơ Sở Dữ Liệu](#6-lưu-trữ-blob--cơ-sở-dữ-liệu)
7. [Bộ Giới Hạn Tốc Độ](#7-bộ-giới-hạn-tốc-độ)
8. [Hệ Thống Giám Sát](#8-hệ-thống-giám-sát)
9. [Hàng Đợi Tin Nhắn Hệ Thống Phân Tán](#9-hàng-đợi-tin-nhắn-hệ-thống-phân-tán)
10. [Bộ Tạo ID Độc Nhất Phân Tán](#10-bộ-tạo-id-độc-nhất-phân-tán)
11. [Tìm Kiếm Phân Tán](#11-tìm-kiếm-phân-tán)
12. [Dịch Vụ Ghi Log Phân Tán](#12-dịch-vụ-ghi-log-phân-tán)
13. [Bộ Lập Lịch Tác Vụ Phân Tán](#13-bộ-lập-lịch-tác-vụ-phân-tán)

## 1. Bộ Cân Bằng Tải
Bộ cân bằng tải là một thành phần trong thiết kế hệ thống có nhiệm vụ phân chia các yêu cầu hoặc khối lượng công việc đến giữa nhiều tài nguyên hoặc máy chủ khác nhau. Điều này hữu ích khi hệ thống có nhiều máy chủ và cần phân chia đều các yêu cầu giữa chúng, hoặc khi hệ thống nhận được số lượng lớn yêu cầu và muốn chia chúng giữa nhiều máy chủ để tránh quá tải bất kỳ máy chủ nào.

Một số loại bộ cân bằng tải phổ biến bao gồm:

- **Bộ cân bằng tải Lớp 4**: Hoạt động ở tầng mạng của mô hình OSI, phân bổ yêu cầu dựa trên số cổng và địa chỉ IP nguồn và đích.
- **Bộ cân bằng tải Lớp 7**: Hoạt động ở tầng ứng dụng của mô hình OSI, phân phối yêu cầu dựa trên nội dung của chúng, bao gồm URL hoặc loại phương thức HTTP.
- **Bộ cân bằng tải toàn cầu**: Được sử dụng trong các hệ thống phân tán để phân phối yêu cầu giữa nhiều máy chủ đặt ở các vùng địa lý khác nhau.
- **Bộ cân bằng tải ứng dụng**: Các bộ cân bằng tải chuyên dụng được thiết kế để làm việc với các loại ứng dụng hoặc giao thức cụ thể, chẳng hạn như HTTP hoặc HTTPS.

## 2. Bộ Nhớ Đệm
Bộ nhớ đệm là kỹ thuật lưu trữ tạm thời dữ liệu được yêu cầu thường xuyên, giúp tăng tốc độ truy xuất khi cần thiết lại. Khi bộ nhớ đệm được bao gồm trong kiến trúc hệ thống, cơ sở dữ liệu chính hoặc nguồn dữ liệu ít bị tải hơn, điều này nâng cao hiệu suất và hiệu quả.

Cách bộ nhớ đệm hoạt động và lợi ích của nó:

- **Truy Cập Nhanh**: Khi dữ liệu được lưu vào bộ nhớ đệm, nó được lưu trữ trong một kho lưu trữ tạm thời nhanh hơn (như bộ nhớ) thay vì được lấy đi lấy lại từ nguồn lưu trữ chậm hơn. Điều này làm cho việc truy xuất thông tin nhanh hơn.
- **Giảm Tải Cơ Sở Dữ Liệu**: Hệ thống có thể xử lý nhiều yêu cầu hơn mà không bị chậm trễ bằng cách giữ dữ liệu thường dùng hoặc phổ biến trong bộ nhớ đệm thay vì liên tục truy vấn cơ sở dữ liệu chính.
- **Cải Thiện Trải Nghiệm Người Dùng**: Truy cập dữ liệu nhanh hơn đồng nghĩa với thời gian phản hồi nhanh hơn cho người dùng, cải thiện trải nghiệm tổng thể trên trang web hoặc ứng dụng.

## 3. Mạng Phân Phối Nội Dung (CDN)
Mạng Phân Phối Nội Dung (CDN) là một mạng lưới các máy chủ phân bố trên các khu vực khác nhau, cho phép phân phối nội dung như trang web, phim và hình ảnh nhanh hơn đến người dùng. CDN được sử dụng trong hầu hết các thiết kế hệ thống để tăng tốc độ và độ tin cậy của việc phân phối nội dung đến người tiêu dùng, đặc biệt khi họ được phân tán ở nhiều vị trí địa lý khác nhau.

**Cách CDN hoạt động**: Khi người dùng yêu cầu nội dung (như video hoặc hình ảnh), thay vì lấy từ máy chủ chính, yêu cầu được xử lý bởi máy chủ CDN gần nhất, nơi có bản sao được lưu trong bộ nhớ đệm của nội dung đó. Điều này giảm khoảng cách dữ liệu phải đi, giúp tải nhanh hơn cho người dùng.

## 4. Cổng API
Cổng API giống như một cửa trung tâm hoặc "bộ điều khiển giao thông" cho các yêu cầu đi vào hệ thống. Trong thiết kế hệ thống, nó đóng vai trò là điểm đầu vào duy nhất cho các khách hàng (như ứng dụng hoặc trang web) để truy cập nhiều dịch vụ backend một cách có tổ chức và an toàn.

Cách nó hoạt động:

- **Định Tuyến Yêu Cầu**: Khách hàng gửi yêu cầu đến Cổng API khi muốn thông tin hoặc hành động từ nhiều dịch vụ. Sau khi chuyển tiếp yêu cầu đến các dịch vụ thích hợp, cổng tổng hợp câu trả lời của họ và cung cấp cho khách hàng một phản hồi thống nhất duy nhất.
- **Đơn Giản Hóa Tương Tác Khách Hàng**: Không có Cổng API, khách hàng có thể cần kết nối trực tiếp với từng dịch vụ riêng lẻ, điều này có thể phức tạp. Cổng API đơn giản hóa điều này bằng cách ẩn chi tiết backend khỏi khách hàng.
- **Bảo Mật và Giám Sát**: Cổng có thể xử lý các tính năng bảo mật như xác thực (kiểm tra danh tính người dùng) và ủy quyền (kiểm tra những gì họ được phép làm). Nó cũng giúp giám sát lưu lượng, để bạn có thể theo dõi và ghi lại việc sử dụng, phát hiện vấn đề hoặc ngăn chặn tấn công.
- **Quản Lý Tải**: Trong các hệ thống bận rộn, cổng có thể giúp cân bằng và kiểm soát luồng yêu cầu để ngăn quá tải, đảm bảo hiệu suất mượt mà hơn.

## 5. Kho Lưu Trữ Khóa-Giá Trị
Kho lưu trữ khóa-giá trị là một loại cơ sở dữ liệu NoSQL được thiết kế để lưu trữ dữ liệu dưới dạng một tập hợp các cặp khóa-giá trị. Mỗi phần dữ liệu được lưu trong kho lưu trữ khóa-giá trị dưới một khóa riêng biệt, và dữ liệu đó đóng vai trò là giá trị. Vì kho lưu trữ khóa-giá trị cho phép truy cập nhanh đến dữ liệu bằng khóa, chúng thường được sử dụng để lưu trữ dữ liệu được truy cập thường xuyên.

Kho lưu trữ khóa-giá trị có nhiều dạng khác nhau, chẳng hạn như:
- **Kho lưu trữ khóa-giá trị trong bộ nhớ**: Lưu trữ dữ liệu trong bộ nhớ để truy cập nhanh.
- **Kho lưu trữ khóa-giá trị bền vững**: Lưu trữ dữ liệu trên đĩa hoặc trong hệ thống tệp phân tán để đảm bảo độ bền.

Kho lưu trữ khóa-giá trị thường đơn giản hơn để sử dụng và có khả năng mở rộng hơn các loại cơ sở dữ liệu khác, như RDBMS. Tuy nhiên, chúng không phù hợp cho việc lưu trữ dữ liệu có cấu trúc phức tạp đòi hỏi khả năng truy vấn nâng cao.

## 6. Lưu Trữ Blob & Cơ Sở Dữ Liệu
Lưu trữ blob và hệ thống cơ sở dữ liệu là hai loại hệ thống lưu trữ khác nhau có thể được sử dụng để lưu trữ và quản lý dữ liệu.

**Lưu trữ blob** (còn được gọi là lưu trữ đối tượng) có thể lưu trữ khối lượng lớn dữ liệu không có cấu trúc, bao gồm tài liệu, hình ảnh, video và tệp âm thanh. Nhìn chung, hệ thống lưu trữ blob rất có khả năng mở rộng và có thể quản lý nhiều yêu cầu cùng lúc. Chúng được sử dụng rộng rãi để lưu trữ nội dung thường xuyên truy cập, chẳng hạn như nội dung do người dùng tạo ra hoặc tệp đa phương tiện.

**Hệ thống cơ sở dữ liệu**, mặt khác, được thiết kế để chứa dữ liệu có cấu trúc đã được sắp xếp theo một cách cụ thể. RDBMS, cơ sở dữ liệu NoSQL và cơ sở dữ liệu trong bộ nhớ là một số loại hệ thống cơ sở dữ liệu. Hệ thống cơ sở dữ liệu thường được sử dụng để lưu trữ dữ liệu cần được truy vấn và truy cập theo cách có cấu trúc, như hồ sơ khách hàng hoặc giao dịch tài chính.

## 7. Bộ Giới Hạn Tốc Độ
Bộ giới hạn tốc độ là các thành phần thiết kế hệ thống được sử dụng để hạn chế tốc độ mà hệ thống hoặc ứng dụng phản hồi các yêu cầu hoặc thực hiện các tác vụ cụ thể. Điều này có thể hữu ích trong nhiều tình huống khác nhau, chẳng hạn như khi hệ thống phải bảo vệ khỏi việc nhận quá nhiều yêu cầu hoặc khi một công ty muốn ngăn một người dùng cụ thể hoặc nhóm người dùng gửi quá nhiều yêu cầu có thể ảnh hưởng đến hiệu suất của hệ thống.

Một số loại bộ giới hạn tốc độ phổ biến bao gồm:

- **Bộ giới hạn tốc độ yêu cầu**: Được sử dụng để giới hạn số lượng yêu cầu mà một hệ thống hoặc ứng dụng xử lý trong một khoảng thời gian nhất định.
- **Bộ giới hạn tốc độ người dùng**: Được sử dụng để giới hạn tốc độ mà một người dùng cụ thể hoặc nhóm người dùng có thể gửi yêu cầu đến hệ thống hoặc ứng dụng.
- **Bộ giới hạn tốc độ kiểu token bucket**: Được sử dụng để giới hạn tốc độ mà các yêu cầu được xử lý bởi hệ thống bằng cách cho phép một số lượng yêu cầu nhất định được xử lý trong mỗi khoảng thời gian, với bất kỳ yêu cầu dư thừa nào được giữ trong một "bucket" cho đến khoảng thời gian tiếp theo.

## 8. Hệ Thống Giám Sát
Hệ thống giám sát là một thành phần thiết kế hệ thống được sử dụng để thu thập, phân tích và báo cáo về các số liệu và dữ liệu hiệu suất khác nhau liên quan đến hệ thống hoặc ứng dụng. Điều này có thể hữu ích trong nhiều kịch bản khác nhau, chẳng hạn như khi hệ thống cần theo dõi hiệu suất và tính khả dụng của chính nó, hoặc khi một tổ chức cần giám sát hiệu suất của các hệ thống và ứng dụng để đảm bảo rằng chúng đáp ứng các cấp độ dịch vụ mong muốn.

Một số loại hệ thống giám sát phổ biến bao gồm:

- **Hệ thống giám sát mạng**: Được sử dụng để giám sát hiệu suất của mạng và các thành phần khác nhau của nó, chẳng hạn như router, switch và máy chủ.
- **Hệ thống giám sát hệ thống**: Được sử dụng để giám sát hiệu suất của hệ thống máy tính và các thành phần khác nhau của nó, chẳng hạn như CPU, bộ nhớ và việc sử dụng đĩa.
- **Hệ thống giám sát ứng dụng**: Được sử dụng để giám sát hiệu suất của các ứng dụng hoặc dịch vụ cụ thể,
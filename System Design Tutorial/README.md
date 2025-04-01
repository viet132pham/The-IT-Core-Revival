# System Design Tutorial 🏗️

## Table of Contents 📑

### Introduction 🚀
- 🔹 What is System Design?
- 🔹 Importance of System Design in Software Development
- 🔹 What to Expect from This System Design Tutorial?

### Basics of System Design 🧱
- 🔹 What is System Design?
- 🔹 What is the Requirements Gathering Process?
- 🔹 Functional vs Non-Functional Requirements
- 🔹 Components of System Design
- 🔹 System Design Life Cycle | SDLC (Design)

### Scalability in System Design 📈
- 🔹 Scalability and How to achieve it
- 🔹 Horizontal and Vertical Scaling
- 🔹 Which Scalability approach is right for our Application?
- 🔹 Primary Bottlenecks that Hurt the Scalability of an Application

### System Architectural Styles 🏛️
- 🔹 Monolithic Architecture
- 🔹 Microservices Architecture
- 🔹 Monolithic vs Microservices Architecture
- 🔹 Event-Driven Architecture
- 🔹 Serverless Architecture

### High-Level Design(HLD) ⚙️
- 🔹 What is High Level Design?
- 🔹 Availability in System Design
- 🔹 Consistency in System Design
- 🔹 Reliability in System Design
- 🔹 CAP Theorem
- 🔹 Difference between Concurrency and Parallelism
- 🔹 Load Balancer
- 🔹 Consistent Hashing
- 🔹 Content Delivery Network(CDN)
- 🔹 Latency and Throughput
- 🔹 Caching in System Design
- 🔹 What is API Gateway
- 🔹 Message Queues
- 🔹 Communication Protocols
- 🔹 Network Protocols and Proxies
- 🔹 Unified Modeling Language (UML)

### Databases in Designing Systems 💾
- 🔹 Which Database to Choose while designing a system – SQL or NoSQL
- 🔹 File and Database Storage Systems
- 🔹 Database Replication in System Design
- 🔹 Database Sharding
- 🔹 Block, Object, and File Storage
- 🔹 Normalization Process in DBMS
- 🔹 Denormalization in Databases

### Low Level Design(LLD) 🔍
- 🔹 What is Low Level Design or LLD
- 🔹 Object-Oriented Programing(OOP) Concepts
- 🔹 Data Structures and Algorithms for System Design
- 🔹 Object-Oriented Analysis and Design
- 🔹 Difference between Authentication and Authorization
- 🔹 Design Patterns
- 🔹 Unit Testing
- 🔹 Integration Testing
- 🔹 CI/CD Pipeline
- 🔹 Introduction to Modularity and Interfaces
- 🔹 Essential Security Measures in System Design

### Interview Questions & Answers of System Design 💼
- 🔹 URL Shortening Service
- 🔹 Design Dropbox
- 🔹 Design Twitter
- 🔹 System Design Netflix – Complete Architecture
- 🔹 System Design of Uber App – Uber System Architecture
- 🔹 Design BookMyShow
- 🔹 Designing Facebook Messenger
- 🔹 Designing Whatsapp Messenger
- 🔹 Designing Instagram
- 🔹 Tips for System Design interview
- 🔹 How to Crack System Design Round in Interviews?
- 🔹 5 Tips to Crack Low-Level System Design Interviews
- 🔹 5 Common System Design Concepts for Interview Preparation
- 🔹 6 Steps To Approach Object-Oriented Design Questions in Interview

### Advantages of System Design ✅
- 🔹 Easy to See How All Parts Connect and Interact
- 🔹 Helps Teams Plan Resources, Time, and Costs Effectively
- 🔹 Easy to Maintain and Update
- 🔹 Allows System to Grow Smoothly
- 🔹 Enhances System Performance

### Disadvantages of System Design ⚠️
- 🔹 Time-Consuming
- 🔹 Expensive
- 🔹 Requires Significant Technical Expertise
- 🔹 Difficult to Change Once Complete

### Reference Books 📚
- 🔹 "Design Patterns: Elements of Reusable Object-Oriented Software" by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides
- 🔹 "The Design of Everyday Things" by Don Norman
- 🔹 "Systems Analysis and Design" by Alan Dennis and Barbara Haley Wixom
- 🔹 "Clean Architecture: A Craftsman's Guide to Software Structure and Design" by Robert C. Martin
- 🔹 "Software Architecture in Practice" by Len Bass, Paul Clements, and Rick Kazman

-----

# Hướng Dẫn Thiết Kế Hệ Thống 🏗️

## Mục Lục 📑

### Giới Thiệu 🚀
- 🔹 Thiết Kế Hệ Thống Là Gì?
- 🔹 Tầm Quan Trọng Của Thiết Kế Hệ Thống Trong Phát Triển Phần Mềm
- 🔹 Điều Gì Mong Đợi Từ Hướng Dẫn Thiết Kế Hệ Thống Này?

### Cơ Bản Về Thiết Kế Hệ Thống 🧱
- 🔹 Thiết Kế Hệ Thống Là Gì?
- 🔹 Quy Trình Thu Thập Yêu Cầu Là Gì?
- 🔹 Yêu Cầu Chức Năng và Phi Chức Năng
- 🔹 Các Thành Phần Của Thiết Kế Hệ Thống
- 🔹 Vòng Đời Thiết Kế Hệ Thống | SDLC (Thiết Kế)

### Khả Năng Mở Rộng Trong Thiết Kế Hệ Thống 📈
- 🔹 Khả Năng Mở Rộng và Cách Đạt Được
- 🔹 Mở Rộng Theo Chiều Ngang và Chiều Dọc
- 🔹 Cách Tiếp Cận Mở Rộng Nào Phù Hợp Cho Ứng Dụng Của Chúng Ta?
- 🔹 Các Điểm Nghẽn Chính Ảnh Hưởng Đến Khả Năng Mở Rộng Của Ứng Dụng

### Phong Cách Kiến Trúc Hệ Thống 🏛️
- 🔹 Kiến Trúc Nguyên Khối
- 🔹 Kiến Trúc Microservices
- 🔹 So Sánh Kiến Trúc Nguyên Khối và Microservices
- 🔹 Kiến Trúc Hướng Sự Kiện
- 🔹 Kiến Trúc Serverless

### Thiết Kế Mức Cao (HLD) ⚙️
- 🔹 Thiết Kế Mức Cao Là Gì?
- 🔹 Tính Khả Dụng Trong Thiết Kế Hệ Thống
- 🔹 Tính Nhất Quán Trong Thiết Kế Hệ Thống
- 🔹 Độ Tin Cậy Trong Thiết Kế Hệ Thống
- 🔹 Định Lý CAP
- 🔹 Sự Khác Biệt Giữa Đồng Thời và Song Song
- 🔹 Cân Bằng Tải
- 🔹 Consistent Hashing
- 🔹 Mạng Phân Phối Nội Dung (CDN)
- 🔹 Độ Trễ và Thông Lượng
- 🔹 Bộ Nhớ Đệm Trong Thiết Kế Hệ Thống
- 🔹 API Gateway Là Gì
- 🔹 Hàng Đợi Tin Nhắn
- 🔹 Giao Thức Truyền Thông
- 🔹 Giao Thức Mạng và Proxy
- 🔹 Ngôn Ngữ Mô Hình Hóa Thống Nhất (UML)

### Cơ Sở Dữ Liệu Trong Thiết Kế Hệ Thống 💾
- 🔹 Lựa Chọn Cơ Sở Dữ Liệu Khi Thiết Kế Hệ Thống - SQL hay NoSQL
- 🔹 Hệ Thống Lưu Trữ Tệp và Cơ Sở Dữ Liệu
- 🔹 Sao Chép Cơ Sở Dữ Liệu Trong Thiết Kế Hệ Thống
- 🔹 Phân Mảnh Cơ Sở Dữ Liệu
- 🔹 Lưu Trữ Khối, Đối Tượng và Tệp
- 🔹 Quy Trình Chuẩn Hóa Trong DBMS
- 🔹 Phi Chuẩn Hóa Trong Cơ Sở Dữ Liệu

### Thiết Kế Mức Thấp (LLD) 🔍
- 🔹 Thiết Kế Mức Thấp Là Gì?
- 🔹 Khái Niệm Lập Trình Hướng Đối Tượng (OOP)
- 🔹 Cấu Trúc Dữ Liệu và Thuật Toán Cho Thiết Kế Hệ Thống
- 🔹 Phân Tích và Thiết Kế Hướng Đối Tượng
- 🔹 Sự Khác Biệt Giữa Xác Thực và Ủy Quyền
- 🔹 Mẫu Thiết Kế
- 🔹 Kiểm Thử Đơn Vị
- 🔹 Kiểm Thử Tích Hợp
- 🔹 CI/CD Pipeline
- 🔹 Giới Thiệu về Tính Mô-đun và Giao Diện
- 🔹 Các Biện Pháp Bảo Mật Thiết Yếu Trong Thiết Kế Hệ Thống

### Câu Hỏi & Trả Lời Phỏng Vấn Về Thiết Kế Hệ Thống 💼
- 🔹 Dịch Vụ Rút Gọn URL
- 🔹 Thiết Kế Dropbox
- 🔹 Thiết Kế Twitter
- 🔹 Thiết Kế Hệ Thống Netflix - Kiến Trúc Hoàn Chỉnh
- 🔹 Thiết Kế Hệ Thống Ứng Dụng Uber - Kiến Trúc Hệ Thống Uber
- 🔹 Thiết Kế BookMyShow
- 🔹 Thiết Kế Facebook Messenger
- 🔹 Thiết Kế Whatsapp Messenger
- 🔹 Thiết Kế Instagram
- 🔹 Mẹo Cho Phỏng Vấn Thiết Kế Hệ Thống
- 🔹 Làm Thế Nào Để Vượt Qua Vòng Thiết Kế Hệ Thống Trong Phỏng Vấn?
- 🔹 5 Mẹo Để Vượt Qua Phỏng Vấn Thiết Kế Hệ Thống Mức Thấp
- 🔹 5 Khái Niệm Thiết Kế Hệ Thống Phổ Biến Cho Việc Chuẩn Bị Phỏng Vấn
- 🔹 6 Bước Tiếp Cận Câu Hỏi Thiết Kế Hướng Đối Tượng Trong Phỏng Vấn

### Ưu Điểm của Thiết Kế Hệ Thống ✅
- 🔹 Dễ Dàng Nhìn Thấy Sự Kết Nối và Tương Tác Giữa Các Phần
- 🔹 Giúp Đội Ngũ Lập Kế Hoạch Tài Nguyên, Thời Gian và Chi Phí Hiệu Quả
- 🔹 Dễ Dàng Bảo Trì và Cập Nhật
- 🔹 Cho Phép Hệ Thống Phát Triển Mượt Mà
- 🔹 Nâng Cao Hiệu Suất Hệ Thống

### Nhược Điểm của Thiết Kế Hệ Thống ⚠️
- 🔹 Tốn Thời Gian
- 🔹 Chi Phí Cao
- 🔹 Yêu Cầu Chuyên Môn Kỹ Thuật Đáng Kể
- 🔹 Khó Thay Đổi Sau Khi Hoàn Thành

### Sách Tham Khảo 📚
- 🔹 "Design Patterns: Elements of Reusable Object-Oriented Software" - Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides
- 🔹 "The Design of Everyday Things" - Don Norman
- 🔹 "Systems Analysis and Design" - Alan Dennis và Barbara Haley Wixom
- 🔹 "Clean Architecture: A Craftsman's Guide to Software Structure and Design" - Robert C. Martin
- 🔹 "Software Architecture in Practice" - Len Bass, Paul Clements, và Rick Kazman

---
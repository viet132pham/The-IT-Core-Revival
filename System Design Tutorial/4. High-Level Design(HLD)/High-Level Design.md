# High-Level Design (HLD)

## What is High-Level Design?

In developing scalable applications, proper planning and organization play a significant role. High-level design plays an important role in this process by serving as the blueprint of the system's architecture. It provides a comprehensive view of how components interact and function together, which will further help for detailed implementation.

High-Level Design is an initial step in development of applications where the overall structure of a system is planned. High-Level design focuses mainly on how different components of the system work together without getting to know about internal coding and implementation. This helps everyone involving in the project to understand the goals and ensures good communication during development.

## Components of High-Level Design

Understanding the components of high-level design is very important for creating effective systems that meet user needs and technical requirements. Below are the main components of high-level design:

1. **System Architecture**: System architecture is an overview of the entire system which represents the structure and the relationships between various components. It helps to visually represent how different parts interact and function.

2. **Modules and Components**: High-Level design breaks down the systems into modules or components, each with specific roles and responsibilities, and has a distinct function that contributes to the entire system helping in developing an efficient system.

3. **Data Flow Diagrams (DFDs)**: Data Flow Diagrams demonstrate the data movement within the system. They help to understand how information is processed and handled.

4. **Interface Design**: This component focuses on how different modules communicate with one another. It details the application programming interfaces (APIs) and user interfaces necessary for seamless interaction between components.

5. **Technology Stack**: The technology stack includes various technologies and tools that will be used in the development of the system. This includes programming languages, frameworks, databases.

6. **Deployment Architecture**: It includes how the system will be hosted and accessed. It includes server configurations, cloud infrastructure, and network considerations.

## What is High-Level Design Document?

HLD document consists of data flows, flowcharts, and data structures to help developers in understanding and implementing how the current system is being designed intentionally to function. This document is responsible for explaining the connections between system components and operations which depict the logic. The architecture design needed (for the system's functionality and flow) for each and every module of the system as per the functional requirements.

## Purpose and Characteristics of High-Level Design

The purpose of this High-Level Design (HLD) is to add the necessary detailed description to represent a suitable model. This is designed to help with operational requirements and will help to understand how the modules interact. Basically, HLD is a technical representation of functional requirements and the flow of information across components.

Characteristics of High-Level Design include:

- A diagram representing each design aspect is included in the HLD (which is based on business requirements and anticipated results).
- Description of hardware, software interfaces, and also user interfaces.
- The workflow of the user's typical process is detailed, along with performance specifications.

## How HLD is different from LLD

High Level Design or HLD is a general system design where we do tradeoffs between different frameworks, components, and different databases and we choose the best considering what the business needs and how the system should work, both in terms of functional and non-functional aspects.

Whereas LLD (Low Level Design), translates the HLD into smaller and more specific details. It includes class diagrams, methods, data structures, and algorithms, focusing on how each part will be implemented.

## How To Design Scalable High-level Design (HLD) Systems

### 1. Capacity Estimation

Capacity estimation in system design involves predicting the resources (such as processing power, memory, and bandwidth) required to meet the expected workload. It ensures that a system can handle current and future demands efficiently, helping in the proper allocation of resources and preventing performance bottlenecks.

For example: Twitter which is recently in newsfeeds these days, here at high-level designing we need to make sure tweets of popular influencers are reaching out to millions of people so how we need to scale our system so service should not be hampered.

---

# Thiết kế cấp cao (High-Level Design - HLD)

## Thiết kế cấp cao là gì?

Trong việc phát triển các ứng dụng có khả năng mở rộng, việc lập kế hoạch và tổ chức đóng vai trò quan trọng. Thiết kế cấp cao đóng một vai trò quan trọng trong quá trình này bằng cách đóng vai trò như bản thiết kế kiến trúc của hệ thống. Nó cung cấp cái nhìn tổng quan về cách các thành phần tương tác và hoạt động cùng nhau, điều này sẽ hỗ trợ cho việc triển khai chi tiết sau này.

Thiết kế cấp cao là bước đầu tiên trong quá trình phát triển các ứng dụng, nơi cấu trúc tổng thể của hệ thống được lập kế hoạch. Thiết kế cấp cao tập trung chủ yếu vào cách các thành phần khác nhau của hệ thống làm việc cùng nhau mà không đi sâu vào mã nguồn và triển khai nội bộ. Điều này giúp mọi người tham gia vào dự án hiểu được mục tiêu và đảm bảo giao tiếp tốt trong quá trình phát triển.

## Các thành phần của Thiết kế cấp cao

Hiểu về các thành phần của thiết kế cấp cao rất quan trọng để tạo ra các hệ thống hiệu quả đáp ứng nhu cầu của người dùng và yêu cầu kỹ thuật. Dưới đây là các thành phần chính của thiết kế cấp cao:

1. **Kiến trúc hệ thống**: Kiến trúc hệ thống là cái nhìn tổng quan về toàn bộ hệ thống, thể hiện cấu trúc và mối quan hệ giữa các thành phần khác nhau. Nó giúp biểu diễn trực quan cách các bộ phận khác nhau tương tác và hoạt động.

2. **Mô-đun và Thành phần**: Thiết kế cấp cao chia hệ thống thành các mô-đun hoặc thành phần, mỗi thành phần có vai trò và trách nhiệm cụ thể, và có chức năng riêng biệt góp phần vào toàn bộ hệ thống, giúp phát triển một hệ thống hiệu quả.

3. **Sơ đồ luồng dữ liệu (DFDs)**: Sơ đồ luồng dữ liệu thể hiện sự di chuyển dữ liệu trong hệ thống. Chúng giúp hiểu cách thông tin được xử lý và quản lý.

4. **Thiết kế giao diện**: Thành phần này tập trung vào cách các mô-đun khác nhau giao tiếp với nhau. Nó chi tiết hóa các giao diện lập trình ứng dụng (APIs) và giao diện người dùng cần thiết cho sự tương tác liền mạch giữa các thành phần.

5. **Công nghệ sử dụng**: Các công nghệ bao gồm các công nghệ và công cụ khác nhau sẽ được sử dụng trong quá trình phát triển hệ thống. Bao gồm ngôn ngữ lập trình, framework, cơ sở dữ liệu.

6. **Kiến trúc triển khai**: Bao gồm cách hệ thống sẽ được lưu trữ và truy cập. Bao gồm cấu hình máy chủ, cơ sở hạ tầng đám mây, và các vấn đề về mạng.

## Tài liệu Thiết kế cấp cao là gì?

Tài liệu HLD bao gồm các luồng dữ liệu, lưu đồ và cấu trúc dữ liệu để giúp các nhà phát triển hiểu và triển khai cách hệ thống hiện tại được thiết kế để hoạt động. Tài liệu này chịu trách nhiệm giải thích các kết nối giữa các thành phần hệ thống và các hoạt động mô tả logic. Thiết kế kiến trúc cần thiết (cho chức năng và luồng của hệ thống) cho từng mô-đun của hệ thống theo các yêu cầu chức năng.

## Mục đích và đặc điểm của Thiết kế cấp cao

Mục đích của Thiết kế cấp cao (HLD) là để bổ sung các mô tả chi tiết cần thiết để đại diện cho một mô hình phù hợp. Nó được thiết kế để hỗ trợ các yêu cầu hoạt động và sẽ giúp hiểu cách các mô-đun tương tác. Về cơ bản, HLD là biểu diễn kỹ thuật của các yêu cầu chức năng và luồng thông tin qua các thành phần.

Các đặc điểm của Thiết kế cấp cao bao gồm:

- Một sơ đồ đại diện cho mỗi khía cạnh thiết kế được đưa vào HLD (dựa trên yêu cầu kinh doanh và kết quả dự kiến).
- Mô tả về phần cứng, giao diện phần mềm, và cũng như giao diện người dùng.
- Quy trình làm việc của quá trình điển hình của người dùng được mô tả chi tiết, cùng với các thông số hiệu suất.

## HLD khác với LLD như thế nào

Thiết kế cấp cao (HLD) là thiết kế hệ thống tổng quát nơi chúng ta đánh đổi giữa các framework, thành phần và các cơ sở dữ liệu khác nhau và chúng ta chọn cái tốt nhất xem xét đến nhu cầu kinh doanh và cách hệ thống nên hoạt động, cả về mặt chức năng và phi chức năng.

Trong khi đó, LLD (Thiết kế cấp thấp) chuyển đổi HLD thành các chi tiết nhỏ hơn và cụ thể hơn. Nó bao gồm sơ đồ lớp, phương thức, cấu trúc dữ liệu, và thuật toán, tập trung vào cách từng phần sẽ được triển khai.

## Cách thiết kế Hệ thống Thiết kế cấp cao (HLD) có khả năng mở rộng

### 1. Ước lượng năng lực

Ước lượng năng lực trong thiết kế hệ thống liên quan đến việc dự đoán các tài nguyên (như sức mạnh xử lý, bộ nhớ và băng thông) cần thiết để đáp ứng khối lượng công việc dự kiến. Nó đảm bảo rằng hệ thống có thể xử lý các yêu cầu hiện tại và tương lai một cách hiệu quả, giúp phân bổ tài nguyên phù hợp và ngăn chặn các nút thắt cổ chai về hiệu suất.

Ví dụ: Twitter, gần đây đang xuất hiện trên các bản tin, tại thiết kế cấp cao, chúng ta cần đảm bảo rằng các tweet của những người có ảnh hưởng nổi tiếng được tiếp cận đến hàng triệu người, vì vậy chúng ta cần mở rộng hệ thống như thế nào để dịch vụ không bị ảnh hưởng.
# CAP Theorem in System Design

## What is the CAP Theorem?

The CAP Theorem explains the trade-offs in distributed systems. It states that a system can only guarantee two of three properties: Consistency, Availability, and Partition Tolerance. This means no system can do it all, so designers must make smart choices based on their needs.

According to the CAP theorem, only two of the three desirable database characteristics—consistency, availability, and partition tolerance—can be guaranteed simultaneously by a networked shared-data system or distributed system.

The computer scientist Eric Brewer presented the CAP Theorem, also called Brewer's theorem, at the Symposium on Principles of Distributed Computing in 2000.

- The theorem provides a way of thinking about the trade-offs involved in designing and building distributed systems.
- It helps to explain why certain types of systems may be more appropriate for certain use cases.
- According to Brewer, the theorem states that a distributed system can have at most two of these guarantees.

## Properties of CAP Theorem

The CAP Theorem refers to three distributed system characteristics:

![CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182147/CAP-Theorem-1.png)

### 1. Consistency

Consistency defines that all clients see the same data simultaneously, no matter which node they connect to in a distributed system. For eventual consistency, the guarantees are a bit looser. Eventual consistency guarantee means clients will eventually see the same data on all the nodes at some point of time in the future.

![Consistency](https://media.geeksforgeeks.org/wp-content/uploads/20230621181957/Consistency.png)

Explanation of the above diagram:
- All nodes have access to the same data at the same time, ensuring uniformity across the distributed system.
- When data is updated at one node, the change is immediately propagated to all other nodes before confirming the update.
- This prevents different nodes from having different views of the data, eliminating discrepancies in the system.

### 2. Availability

Availability means every request receives a response, whether successful or not. This is a crucial aspect of availability, as it guarantees that users always get feedback.

![Availability](https://media.geeksforgeeks.org/wp-content/uploads/20230621182044/Availability.png)

Explanation of the above diagram:
- Every node in the distributed system must be able to respond to requests, ensuring that the system remains operational for users.
- The system continues to function even if one or more nodes are experiencing issues, maintaining a high level of service availability.
- Typically measured in terms of uptime percentage, like "99.9% availability."

### 3. Partition Tolerance

Partition Tolerance defines that the system continues to operate despite arbitrary message loss or failure in parts of the system. Distributed systems guaranteeing partition tolerance can gracefully recover from partitions once the partition heals.

![Partition-Tolerance](https://media.geeksforgeeks.org/wp-content/uploads/20230621182117/Partition-Tolerance.png)

Explanation of the above diagram:
- Addresses network failures, a common cause of partitions. It suggests that the system is designed to function even when parts of the network become unreachable.
- The system can adapt to arbitrary partitioning, meaning it can handle unpredictable network failures without complete failure.

## Trade-Offs in the CAP Theorem

We can classify the systems into the following three categories:

![Trade-off-in-the-CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182215/Trade-off-in-the-CAP-Theorem.png)

### 1. CA System

A CA System delivers consistency and availability across all the nodes. It can't do this if there is a partition between any two nodes in the system and therefore doesn't support partition tolerance.

### 2. CP System

A CP System delivers consistency and partition tolerance at the expense of availability. When a partition occurs between two nodes, the system shuts down the non-available node until the partition is resolved. Some examples of CP databases are MongoDB, Redis, and HBase.

### 3. AP System

An AP System prioritizes availability and partition tolerance at the expense of consistency. When a partition occurs, all nodes remain available, but those at the wrong end of a partition might return an older version of data than others. Examples include CouchDB, Cassandra, and DynamoDB.

## Example to Understand the CAP Theorem

![Example-of-CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182255/Example-of-CAP-Theorem.png)

In the figure above:
- We have a simple distributed system where S1 and S2 are two servers. The two servers can talk to each other. Here, the system is partition tolerant. We will prove that the system can be either consistent or available.
- Suppose there is a network failure and S1 and S2 cannot talk to each other. Now assume that the client makes a write to S1. The client then sends a read to S2.
- Given S1 and S2 cannot talk, they have different views of the data. If the system has to remain consistent, it must deny the request and thus give up on availability.
- If the system is available, then the system has to give up on consistency. This proves the CAP Theorem.

## Use Cases of the CAP Theorem in System Design

Here we will see how we can use all the trade-off systems in real applications:

### 1. Banking Transactions (CP System)

**Problem Statement:**
A banking system needs to ensure that users can't withdraw more money than they have in their accounts, even during network issues.

**Why CP?**
- Banks prioritize consistency and partition tolerance to prevent issues like double spending or incorrect balances.
- During network partitions, the system might temporarily deny service (reduced availability) to ensure all nodes have consistent data about account balances.
- This approach may result in occasional service unavailability but ensures financial data integrity.

### 2. Social Media Feed (AP System)

**Problem Statement:**
A social media platform needs to ensure users can always post updates and view their news feeds, even during system outages.

**Why AP?**
- Users expect immediate access to their newsfeeds (availability) even if parts of the network are temporarily down (partition tolerance). Slight inconsistencies in data, like seeing a friend's post slightly sooner on one device than another, are tolerable in this context.
- Data might not be perfectly consistent across all servers immediately after updates. Users might occasionally see slightly different versions of their newsfeed before data propagates across the system.

### 3. Online Shopping Cart (Hybrid System CAP System)

**Problem Statement:**
Imagine an online shopping cart, adding items, and checking out. This system might employ a hybrid approach balancing CAP trade-offs.

**Why use AP and CP System?**
- Adding items to the cart could be available and partition-tolerant (AP), allowing uninterrupted browsing even if temporary network glitches occur.
- But when confirming the order and processing payment, the system might switch to a CP mode, ensuring consistency across all servers before finalizing the transaction.
- The system requires careful design to switch seamlessly between availability and consistency modes at the right points to handle different stages of the user journey effectively.

## Advantages of CAP Theorem in System Design

1. **Provides a Framework for Decision-Making:**
   - It makes clear the basic decisions that must be made while creating distributed systems.
   - Engineers are forced by this model to clearly prioritize the objectives of their system, which results in more thoughtful and informed design choices.

2. **Promotes Understanding of Trade-offs:**
   - By outlining the limitations of achieving all three CAP properties simultaneously, the theorem prevents unrealistic expectations.
   - This awareness of trade-offs enables designers to make balanced choices that prioritize the most critical properties for their specific context.

3. **Guides System Architecture and Technology Selection:**
   - Understanding the CAP implications helps choose appropriate database technologies, replication strategies, and communication protocols based on the desired properties.

4. **Enhances System Resilience and Performance:**
   - Putting particular CAP combinations into focus results in solutions that are specifically designed to ensure responsiveness under high load (availability) or resilience against network failures (partition tolerance).

## Disadvantages of CAP Theorem in System Design

1. **Oversimplification:**
   - The CAP theorem focuses on three core properties, but real-world systems might involve other crucial factors like performance, data durability, and latency. Neglecting these aspects can lead to incomplete or suboptimal design solutions.

2. **Abstract Trade-offs:**
   - The CAP theorem defines theoretical bounds, but choosing the appropriate CAP combination for a specific application can be challenging. Quantifying the acceptable level of inconsistency or downtime for different scenarios requires careful analysis.

3. **Lack of Guidance for Hybrid Systems:**
   - While the CAP theorem helps choose between prioritized combinations, it doesn't explicitly provide guidance for designing systems that might require switching between different prioritizations at different stages or for specific data subsets.

4. **Potential Misinterpretation:**
   - Misunderstanding the nuances of the CAP theorem can lead to misinformed decisions. For example, prioritizing availability might be misinterpreted as compromising data integrity, resulting in unnecessary sacrifices in consistency when it's not justified.

## Conclusion

CAP theorem is a valuable tool, but it's important to be aware of its limitations and apply it critically within the context of your specific system design challenges. Utilize its insights to make informed decisions, explore hybrid approaches when necessary, and stay open to adapting your solutions as needs and technologies evolve. The CAP theorem, despite highlighting inherent limitations, serves as a valuable guide and decision-making framework for designing reliable, efficient, and user-centric distributed systems.

---

# Định lý CAP trong Thiết kế Hệ thống

## Định lý CAP là gì?

Định lý CAP giải thích sự đánh đổi trong các hệ thống phân tán. Nó nêu rõ rằng một hệ thống chỉ có thể đảm bảo hai trong ba thuộc tính: Tính nhất quán (Consistency), Tính khả dụng (Availability) và Khả năng chịu phân mảnh (Partition Tolerance). Điều này có nghĩa là không có hệ thống nào có thể làm được tất cả, vì vậy các nhà thiết kế phải đưa ra lựa chọn sáng suốt dựa trên nhu cầu của họ.

Theo định lý CAP, chỉ có thể đảm bảo đồng thời hai trong ba đặc tính cơ sở dữ liệu mong muốn—tính nhất quán, tính khả dụng và khả năng chịu phân mảnh—trong một hệ thống dữ liệu được chia sẻ qua mạng hoặc hệ thống phân tán.

Nhà khoa học máy tính Eric Brewer đã trình bày định lý CAP, còn được gọi là định lý Brewer, tại Hội nghị về Nguyên tắc Điện toán Phân tán vào năm 2000.

- Định lý cung cấp một cách suy nghĩ về sự đánh đổi trong việc thiết kế và xây dựng các hệ thống phân tán.
- Nó giúp giải thích tại sao các loại hệ thống nhất định có thể phù hợp hơn cho các trường hợp sử dụng cụ thể.
- Theo Brewer, định lý nêu rõ rằng một hệ thống phân tán có thể có nhiều nhất hai trong số các đảm bảo này.

## Các Thuộc tính của Định lý CAP

Định lý CAP đề cập đến ba đặc tính của hệ thống phân tán:

![CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182147/CAP-Theorem-1.png)

### 1. Tính nhất quán (Consistency)

Tính nhất quán định nghĩa rằng tất cả các máy khách đều nhìn thấy dữ liệu giống nhau cùng một lúc, không quan trọng họ kết nối với nút nào trong hệ thống phân tán. Đối với tính nhất quán cuối cùng, các đảm bảo có phần lỏng lẻo hơn. Đảm bảo tính nhất quán cuối cùng có nghĩa là khách hàng cuối cùng sẽ nhìn thấy cùng một dữ liệu trên tất cả các nút tại một thời điểm nào đó trong tương lai.

![Consistency](https://media.geeksforgeeks.org/wp-content/uploads/20230621181957/Consistency.png)

Giải thích sơ đồ trên:
- Tất cả các nút có quyền truy cập vào cùng một dữ liệu tại cùng một thời điểm, đảm bảo tính đồng nhất trong toàn bộ hệ thống phân tán.
- Khi dữ liệu được cập nhật tại một nút, sự thay đổi được lan truyền ngay lập tức đến tất cả các nút khác trước khi xác nhận cập nhật.
- Điều này ngăn chặn các nút khác nhau có góc nhìn khác nhau về dữ liệu, loại bỏ sự khác biệt trong hệ thống.

### 2. Tính khả dụng (Availability)

Tính khả dụng có nghĩa là mọi yêu cầu đều nhận được phản hồi, cho dù thành công hay không. Đây là một khía cạnh quan trọng của tính khả dụng, vì nó đảm bảo rằng người dùng luôn nhận được phản hồi.

![Availability](https://media.geeksforgeeks.org/wp-content/uploads/20230621182044/Availability.png)

Giải thích sơ đồ trên:
- Mỗi nút trong hệ thống phân tán phải có khả năng đáp ứng các yêu cầu, đảm bảo rằng hệ thống vẫn hoạt động cho người dùng.
- Hệ thống tiếp tục hoạt động ngay cả khi một hoặc nhiều nút đang gặp sự cố, duy trì mức độ khả dụng dịch vụ cao.
- Thường được đo bằng tỷ lệ phần trăm thời gian hoạt động, như "khả dụng 99,9%".

### 3. Khả năng chịu phân mảnh (Partition Tolerance)

Khả năng chịu phân mảnh định nghĩa rằng hệ thống tiếp tục hoạt động bất chấp việc mất tin nhắn tùy ý hoặc lỗi ở các phần của hệ thống. Các hệ thống phân tán đảm bảo khả năng chịu phân mảnh có thể phục hồi một cách nhẹ nhàng từ các phân mảnh khi phân mảnh được khắc phục.

![Partition-Tolerance](https://media.geeksforgeeks.org/wp-content/uploads/20230621182117/Partition-Tolerance.png)

Giải thích sơ đồ trên:
- Giải quyết các lỗi mạng, một nguyên nhân phổ biến của phân mảnh. Nó cho thấy hệ thống được thiết kế để hoạt động ngay cả khi các phần của mạng trở nên không thể truy cập được.
- Hệ thống có thể thích ứng với phân mảnh tùy ý, có nghĩa là nó có thể xử lý các lỗi mạng không thể dự đoán mà không bị lỗi hoàn toàn.

## Sự đánh đổi trong Định lý CAP

Chúng ta có thể phân loại các hệ thống thành ba loại sau:

![Trade-off-in-the-CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182215/Trade-off-in-the-CAP-Theorem.png)

### 1. Hệ thống CA

Một hệ thống CA cung cấp tính nhất quán và tính khả dụng trên tất cả các nút. Nó không thể làm điều này nếu có phân mảnh giữa hai nút bất kỳ trong hệ thống và do đó không hỗ trợ khả năng chịu phân mảnh.

### 2. Hệ thống CP

Một hệ thống CP cung cấp tính nhất quán và khả năng chịu phân mảnh với cái giá là tính khả dụng. Khi xảy ra phân mảnh giữa hai nút, hệ thống sẽ tắt nút không khả dụng cho đến khi phân mảnh được giải quyết. Một số ví dụ về cơ sở dữ liệu CP là MongoDB, Redis và HBase.

### 3. Hệ thống AP

Một hệ thống AP ưu tiên tính khả dụng và khả năng chịu phân mảnh với cái giá là tính nhất quán. Khi xảy ra phân mảnh, tất cả các nút vẫn khả dụng, nhưng những nút ở đầu sai của phân mảnh có thể trả về phiên bản dữ liệu cũ hơn so với các nút khác. Các ví dụ bao gồm CouchDB, Cassandra và DynamoDB.

## Ví dụ để Hiểu Định lý CAP

![Example-of-CAP-Theorem](https://media.geeksforgeeks.org/wp-content/uploads/20230621182255/Example-of-CAP-Theorem.png)

Trong hình trên:
- Chúng ta có một hệ thống phân tán đơn giản trong đó S1 và S2 là hai máy chủ. Hai máy chủ có thể nói chuyện với nhau. Ở đây, hệ thống có khả năng chịu phân mảnh. Chúng tôi sẽ chứng minh rằng hệ thống có thể nhất quán hoặc khả dụng.
- Giả sử có lỗi mạng và S1 và S2 không thể nói chuyện với nhau. Bây giờ giả sử rằng máy khách thực hiện ghi lên S1. Sau đó, máy khách gửi yêu cầu đọc đến S2.
- Do S1 và S2 không thể nói chuyện, chúng có góc nhìn khác nhau về dữ liệu. Nếu hệ thống phải duy trì tính nhất quán, nó phải từ chối yêu cầu và do đó từ bỏ tính khả dụng.
- Nếu hệ thống khả dụng, thì hệ thống phải từ bỏ tính nhất quán. Điều này chứng minh Định lý CAP.

## Các trường hợp sử dụng của Định lý CAP trong Thiết kế Hệ thống

Dưới đây chúng ta sẽ xem cách sử dụng tất cả các hệ thống đánh đổi trong các ứng dụng thực tế:

### 1. Giao dịch Ngân hàng (Hệ thống CP)

**Vấn đề cần giải quyết:**
Một hệ thống ngân hàng cần đảm bảo rằng người dùng không thể rút nhiều tiền hơn số dư trong tài khoản của họ, ngay cả khi xảy ra sự cố mạng.

**Tại sao chọn CP?**
- Ngân hàng ưu tiên tính nhất quán và khả năng chịu phân mảnh để ngăn chặn các vấn đề như chi tiêu gấp đôi hoặc số dư không chính xác.
- Trong các phân mảnh mạng, hệ thống có thể tạm thời từ chối dịch vụ (giảm tính khả dụng) để đảm bảo tất cả các nút đều có dữ liệu nhất quán về số dư tài khoản.
- Cách tiếp cận này có thể dẫn đến dịch vụ không khả dụng thỉnh thoảng nhưng đảm bảo tính toàn vẹn dữ liệu tài chính.

### 2. Nguồn cấp dữ liệu Mạng xã hội (Hệ thống AP)

**Vấn đề cần giải quyết:**
Một nền tảng mạng xã hội cần đảm bảo người dùng luôn có thể đăng cập nhật và xem nguồn cấp tin tức của họ, ngay cả khi hệ thống gặp sự cố.

**Tại sao chọn AP?**
- Người dùng mong đợi truy cập ngay lập tức vào nguồn cấp tin tức của họ (tính khả dụng) ngay cả khi các phần của mạng tạm thời bị ngắt kết nối (khả năng chịu phân mảnh). Các không nhất quán nhỏ trong dữ liệu, như nhìn thấy bài đăng của bạn sớm hơn một chút trên thiết bị này so với thiết bị khác, là có thể chấp nhận được trong ngữ cảnh này.
- Dữ liệu có thể không nhất quán hoàn toàn trên tất cả các máy chủ ngay sau khi cập nhật. Người dùng đôi khi có thể thấy các phiên bản nguồn cấp tin tức của họ hơi khác nhau trước khi dữ liệu lan truyền qua hệ thống.

### 3. Giỏ hàng Mua sắm trực tuyến (Hệ thống CAP kết hợp)

**Vấn đề cần giải quyết:**
Hãy tưởng tượng một giỏ hàng mua sắm trực tuyến, thêm các mặt hàng và thanh toán. Hệ thống này có thể sử dụng cách tiếp cận kết hợp cân bằng các đánh đổi CAP.

**Tại sao sử dụng cả hai hệ thống AP và CP?**
- Việc thêm các mặt hàng vào giỏ hàng có thể khả dụng và chịu được phân mảnh (AP), cho phép duyệt web không bị gián đoạn ngay cả khi xảy ra sự cố mạng tạm thời.
- Nhưng khi xác nhận đơn hàng và xử lý thanh toán, hệ thống có thể chuyển sang chế độ CP, đảm bảo tính nhất quán trên tất cả các máy chủ trước khi hoàn tất giao dịch.
- Hệ thống đòi hỏi thiết kế cẩn thận để chuyển đổi liền mạch giữa các chế độ khả dụng và nhất quán tại các điểm thích hợp để xử lý hiệu quả các giai đoạn khác nhau của hành trình người dùng.

## Ưu điểm của Định lý CAP trong Thiết kế Hệ thống

1. **Cung cấp Khung quyết định:**
   - Nó làm rõ các quyết định cơ bản phải được đưa ra trong khi tạo ra các hệ thống phân tán.
   - Các kỹ sư bị buộc phải ưu tiên rõ ràng các mục tiêu của hệ thống của họ, dẫn đến những lựa chọn thiết kế suy nghĩ và thông tin hơn.

2. **Thúc đẩy Hiểu biết về Sự đánh đổi:**
   - Bằng cách phác thảo những hạn chế của việc đạt được đồng thời cả ba thuộc tính CAP, định lý ngăn chặn các kỳ vọng không thực tế.
   - Nhận thức về sự đánh đổi này cho phép các nhà thiết kế đưa ra các lựa chọn cân bằng, ưu tiên các thuộc tính quan trọng nhất cho bối cảnh cụ thể của họ.

3. **Hướng dẫn Lựa chọn Kiến trúc và Công nghệ Hệ thống:**
   - Hiểu về các tác động của CAP giúp chọn các công nghệ cơ sở dữ liệu, chiến lược sao chép và giao thức truyền thông thích hợp dựa trên các thuộc tính mong muốn.

4. **Nâng cao Khả năng phục hồi và Hiệu suất Hệ thống:**
   - Tập trung vào các kết hợp CAP cụ thể dẫn đến các giải pháp được thiết kế đặc biệt để đảm bảo khả năng đáp ứng dưới tải cao (tính khả dụng) hoặc khả năng chống chịu lỗi mạng (khả năng chịu phân mảnh).

## Nhược điểm của Định lý CAP trong Thiết kế Hệ thống

1. **Đơn giản hóa quá mức:**
   - Định lý CAP tập trung vào ba thuộc tính cốt lõi, nhưng các hệ thống trong thế giới thực có thể liên quan đến các yếu tố quan trọng khác như hiệu suất, độ bền dữ liệu và độ trễ. Bỏ qua các khía cạnh này có thể dẫn đến các giải pháp thiết kế không đầy đủ hoặc không tối ưu.

2. **Sự đánh đổi trừu tượng:**
   - Định lý CAP định nghĩa các ranh giới lý thuyết, nhưng việc chọn kết hợp CAP thích hợp cho một ứng dụng cụ thể có thể đầy thách thức. Định lượng mức độ không nhất quán hoặc thời gian ngừng hoạt động có thể chấp nhận được cho các kịch bản khác nhau đòi hỏi phân tích cẩn thận.

3. **Thiếu hướng dẫn cho các Hệ thống kết hợp:**
   - Mặc dù định lý CAP giúp lựa chọn giữa các kết hợp ưu tiên, nhưng nó không cung cấp hướng dẫn rõ ràng cho việc thiết kế các hệ thống có thể yêu cầu chuyển đổi giữa các ưu tiên khác nhau ở các giai đoạn khác nhau hoặc cho các tập con dữ liệu cụ thể.

4. **Khả năng hiểu sai:**
   - Hiểu sai về các sắc thái của định lý CAP có thể dẫn đến các quyết định không có đầy đủ thông tin. Ví dụ, việc ưu tiên tính khả dụng có thể bị hiểu sai là ảnh hưởng đến tính toàn vẹn dữ liệu, dẫn đến việc hy sinh không cần thiết về tính nhất quán khi nó không được biện minh.

## Kết luận

Định lý CAP là một công cụ có giá trị, nhưng điều quan trọng là phải nhận thức được những hạn chế của nó và áp dụng nó một cách đánh giá trong bối cảnh của các thách thức thiết kế hệ thống cụ thể của bạn. Sử dụng những hiểu biết của nó để đưa ra quyết định có căn cứ, khám phá các cách tiếp cận kết hợp khi cần thiết, và luôn sẵn sàng điều chỉnh các giải pháp của bạn khi nhu cầu và công nghệ phát triển. Định lý CAP, mặc dù nêu bật các hạn chế cố hữu, đóng vai trò như một hướng dẫn có giá trị và khung quyết định cho việc thiết kế các hệ thống phân tán đáng tin cậy, hiệu quả và lấy người dùng làm trung tâm.
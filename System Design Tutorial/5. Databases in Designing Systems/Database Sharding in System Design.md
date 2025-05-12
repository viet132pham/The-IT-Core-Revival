# Database Sharding in System Design

## English Version

Database sharding is a technique for horizontal scaling of databases, where data is split across multiple database instances, or shards, to improve performance and handle large volumes of data more efficiently. It's particularly valuable when a single database instance becomes a bottleneck due to increasing data volume or transaction rates.

## What is Database Sharding?

Sharding is a database architecture pattern in which we split a large dataset into smaller chunks (logical shards) and distribute these chunks across different machines or database nodes (physical shards). Each shard is essentially a separate database instance that holds only a portion of the entire dataset.

To understand sharding, consider a pizza analogy: When you get a pizza, you slice it and share these slices with your friends. Similarly, in database sharding, you're dividing your large database into smaller, more manageable pieces.

Key characteristics of database sharding include:

- Each chunk or partition is known as a "shard"
- Each shard has the same database schema as the original database
- Data is distributed such that each row appears in exactly one shard
- Sharding improves the scalability of an application by distributing the database load

![Database Sharding](https://media.geeksforgeeks.org/wp-content/uploads/20230413115746/Database-Sharding-(1).png)

## Methods of Database Sharding

There are several approaches to implementing database sharding, each with its own advantages and disadvantages. The main sharding strategies include:

### 1. Key-Based Sharding (Hash-Based Sharding)

In key-based sharding, we use a hash function on a specific column (called the shard key) to determine which shard should store a particular row of data.

For example, if we have user data with a user ID as the shard key, we might compute:
```
shard_number = hash(user_id) % number_of_shards
```

This approach evenly distributes data across shards based on the hash value of the shard key.

**Advantages of Key-Based Sharding:**
- Evenly distributes data across shards, preventing hotspots
- Simple to implement and maintain
- Good for write-heavy operations with predictable shard key usage

**Disadvantages of Key-Based Sharding:**
- Difficult to add or remove shards (requires rehashing and data redistribution)
- Range queries across the shard key can be inefficient
- May lead to uneven distribution if the hash function isn't properly designed

### 2. Horizontal or Range-Based Sharding

Range-based sharding partitions data based on ranges of a shard key. Each shard is responsible for storing rows that fall within a specific range of values.

For example, in an e-commerce application, orders might be sharded by date ranges:
- Shard 1: Orders from January to March
- Shard 2: Orders from April to June
- And so on...

**Advantages of Range-Based Sharding:**
- Efficient for range queries within a single shard
- Easier to add new shards without redistributing all data
- Data organization is intuitive and logical

**Disadvantages of Range-Based Sharding:**
- Can lead to uneven data distribution (e.g., some date ranges might have more activity)
- Complex querying across multiple shards
- Potential for "hot spots" where certain ranges receive more queries than others

### 3. Vertical Sharding

In vertical sharding, we split entire columns from a table and place those columns into new distinct tables. Each shard holds both distinct rows and columns, with data being totally independent from one partition to another.

For example, in a social media application like Twitter:
- User profiles could be on one shard
- Followers information on a second shard
- Tweets on a third shard

**Advantages of Vertical Sharding:**
- Query performance improvements as each shard focuses on a specific subset of columns
- Simplified queries for specific sets of columns
- Reduced I/O requirements for queries that only need specific columns

**Disadvantages of Vertical Sharding:**
- Potential for hotspots if certain shards contain highly accessed columns
- Challenges with schema changes across multiple shards
- More complex queries when data from multiple shards is needed

### 4. Directory-Based Sharding

In directory-based sharding, we create and maintain a lookup service or lookup table that maps data to the appropriate shard. The lookup service keeps track of which database shards hold which data.

When a client needs to access data:
1. It queries the lookup service to find the appropriate shard
2. Once it receives the shard location, it queries that specific shard

**Advantages of Directory-Based Sharding:**
- Flexible data distribution that can be dynamically managed
- Efficient query routing
- Dynamic scalability without requiring changes to application logic

**Disadvantages of Directory-Based Sharding:**
- The central directory represents a single point of failure
- Increased latency due to the additional lookup step
- More complex to implement and maintain

## Optimizing Database Sharding for Even Data Distribution

To ensure optimal performance and avoid hotspots in a sharded database system, consider these optimization techniques:

1. **Use Consistent Hashing**: This distributes data more evenly across shards and minimizes data movement when adding or removing shards.

2. **Choose a Good Shard Key**: Select a shard key that distributes data evenly and aligns with your most common query patterns.

3. **Monitor and Rebalance**: Regularly monitor shard usage and performance, rebalancing data across shards as needed.

4. **Consider Composite Shard Keys**: Using multiple columns as a shard key can provide better distribution patterns.

5. **Pre-split Shards**: If you anticipate growth, pre-split your shards to accommodate future data without major redistribution efforts.

## Alternatives to Database Sharding

While sharding is an effective scaling strategy, other approaches might be more suitable depending on your specific requirements:

1. **Vertical Scaling**: Adding more resources (CPU, RAM, storage) to your existing database server.

2. **Replication**: Creating copies of your database on multiple servers to improve read performance and availability.

3. **Partitioning**: Dividing data within the same server into smaller sections to improve query performance.

4. **Caching**: Storing frequently accessed data in a cache system like Redis or Memcached to reduce database load.

5. **CDNs**: Using Content Delivery Networks for read-heavy workloads to offload data access from your primary database.

## Advantages of Sharding in System Design

1. **Enhanced Performance**: By distributing the load across multiple servers, sharding can significantly improve database performance.

2. **Improved Scalability**: Sharding allows for horizontal scaling by adding more database servers as data volume grows.

3. **Increased Availability**: If one shard fails, only a portion of the data becomes unavailable, while the rest of the system continues to function.

4. **Better Resource Utilization**: Sharding allows for more efficient use of resources by distributing data processing across multiple machines.

5. **Geographic Distribution**: Shards can be placed in different geographic locations to reduce latency for users in those regions.

## Disadvantages of Sharding in System Design

1. **Increased Complexity**: Managing and maintaining multiple shards is more complex than working with a single database.

2. **Rebalancing Challenges**: If data distribution becomes uneven, rebalancing shards can be difficult and time-consuming.

3. **Cross-Shard Queries**: Queries that need data from multiple shards can be slower and more complicated to handle.

4. **Operational Overhead**: Sharding requires more monitoring, backups, and maintenance, increasing operational costs.

5. **Potential Data Loss**: If a shard fails without proper backup, there's a higher risk of losing the data stored on that shard.

## When to Use Database Sharding

Consider implementing database sharding when:

1. Your database size exceeds the capacity of a single server
2. Transaction volumes are too high for a single database instance
3. Write operations are creating performance bottlenecks
4. You need to scale beyond the vertical scaling limits of your infrastructure
5. You need to improve performance for specific geographic regions

## Implementation Considerations

When implementing database sharding, consider these key factors:

1. **Shard Key Selection**: The choice of shard key is critical, as it determines how data is distributed across shards.

2. **Query Routing**: Develop a robust mechanism to route queries to the appropriate shard(s).

3. **Cross-Shard Operations**: Design strategies for handling queries that span multiple shards.

4. **Schema Changes**: Plan for how schema changes will be propagated across all shards.

5. **Monitoring and Management**: Implement comprehensive monitoring to identify performance issues and imbalances.

## Conclusion

Database sharding is a powerful technique for scaling databases horizontally when single-server capacity is no longer sufficient. While it introduces complexity in terms of data distribution, query routing, and management, sharding offers significant benefits in terms of performance, scalability, and availability for large-scale applications.

The key to successful sharding lies in choosing the right sharding strategy, selecting appropriate shard keys, and implementing effective mechanisms for query routing and cross-shard operations. When properly implemented, sharding can help your application handle massive growth in data volume and user traffic while maintaining performance and reliability.

---

# Phân Mảnh Cơ Sở Dữ Liệu trong Thiết Kế Hệ Thống

## Phiên Bản Tiếng Việt

Phân mảnh cơ sở dữ liệu là một kỹ thuật để mở rộng theo chiều ngang các cơ sở dữ liệu, trong đó dữ liệu được chia qua nhiều phiên bản cơ sở dữ liệu, hay mảnh, để cải thiện hiệu suất và xử lý khối lượng dữ liệu lớn hiệu quả hơn. Nó đặc biệt có giá trị khi một phiên bản cơ sở dữ liệu đơn lẻ trở thành nút thắt cổ chai do khối lượng dữ liệu hoặc tốc độ giao dịch tăng lên.

## Phân Mảnh Cơ Sở Dữ Liệu là gì?

Phân mảnh là một mô hình kiến trúc cơ sở dữ liệu trong đó chúng ta chia một tập dữ liệu lớn thành những mảnh nhỏ hơn (mảnh logic) và phân phối các mảnh này qua các máy hoặc nút cơ sở dữ liệu khác nhau (mảnh vật lý). Mỗi mảnh về cơ bản là một phiên bản cơ sở dữ liệu riêng biệt chỉ chứa một phần của toàn bộ tập dữ liệu.

Để hiểu phân mảnh, hãy xem xét một ví dụ về pizza: Khi bạn có một chiếc bánh pizza, bạn cắt nó thành từng lát và chia sẻ những lát này với bạn bè. Tương tự, trong phân mảnh cơ sở dữ liệu, bạn đang chia cơ sở dữ liệu lớn của mình thành những phần nhỏ, dễ quản lý hơn.

Các đặc điểm chính của phân mảnh cơ sở dữ liệu bao gồm:

- Mỗi mảnh hoặc phân vùng được gọi là một "mảnh"
- Mỗi mảnh có cùng cấu trúc cơ sở dữ liệu với cơ sở dữ liệu gốc
- Dữ liệu được phân phối sao cho mỗi hàng xuất hiện chính xác trong một mảnh
- Phân mảnh cải thiện khả năng mở rộng của ứng dụng bằng cách phân phối tải cơ sở dữ liệu

## Các Phương Pháp Phân Mảnh Cơ Sở Dữ Liệu

Có một số cách tiếp cận để thực hiện phân mảnh cơ sở dữ liệu, mỗi cách có ưu điểm và nhược điểm riêng. Các chiến lược phân mảnh chính bao gồm:

### 1. Phân Mảnh Dựa Trên Khóa (Phân Mảnh Dựa Trên Hàm Băm)

Trong phân mảnh dựa trên khóa, chúng ta sử dụng một hàm băm trên một cột cụ thể (gọi là khóa phân mảnh) để xác định mảnh nào sẽ lưu trữ một hàng dữ liệu cụ thể.

Ví dụ, nếu chúng ta có dữ liệu người dùng với ID người dùng làm khóa phân mảnh, chúng ta có thể tính:
```
số_mảnh = băm(id_người_dùng) % số_lượng_mảnh
```

Cách tiếp cận này phân phối dữ liệu đều qua các mảnh dựa trên giá trị băm của khóa phân mảnh.

**Ưu điểm của Phân Mảnh Dựa Trên Khóa:**
- Phân phối dữ liệu đều qua các mảnh, ngăn chặn điểm nóng
- Đơn giản để triển khai và duy trì
- Tốt cho các hoạt động ghi nặng với việc sử dụng khóa phân mảnh dự đoán được

**Nhược điểm của Phân Mảnh Dựa Trên Khóa:**
- Khó để thêm hoặc xóa các mảnh (yêu cầu băm lại và phân phối lại dữ liệu)
- Các truy vấn theo phạm vi qua khóa phân mảnh có thể không hiệu quả
- Có thể dẫn đến phân phối không đều nếu hàm băm không được thiết kế đúng cách

### 2. Phân Mảnh Theo Chiều Ngang hoặc Theo Phạm Vi

Phân mảnh dựa trên phạm vi chia dữ liệu dựa trên các phạm vi của khóa phân mảnh. Mỗi mảnh chịu trách nhiệm lưu trữ các hàng nằm trong một phạm vi giá trị cụ thể.

Ví dụ, trong một ứng dụng thương mại điện tử, các đơn hàng có thể được phân mảnh theo phạm vi ngày:
- Mảnh 1: Đơn hàng từ tháng 1 đến tháng 3
- Mảnh 2: Đơn hàng từ tháng 4 đến tháng 6
- Và cứ tiếp tục...

**Ưu điểm của Phân Mảnh Dựa Trên Phạm Vi:**
- Hiệu quả cho các truy vấn phạm vi trong một mảnh đơn lẻ
- Dễ dàng thêm các mảnh mới mà không cần phân phối lại tất cả dữ liệu
- Tổ chức dữ liệu có tính trực quan và logic

**Nhược điểm của Phân Mảnh Dựa Trên Phạm Vi:**
- Có thể dẫn đến phân phối dữ liệu không đều (ví dụ, một số phạm vi ngày có thể có nhiều hoạt động hơn)
- Truy vấn phức tạp qua nhiều mảnh
- Tiềm ẩn "điểm nóng" khi một số phạm vi nhận được nhiều truy vấn hơn những phạm vi khác

### 3. Phân Mảnh Theo Chiều Dọc

Trong phân mảnh theo chiều dọc, chúng ta tách toàn bộ các cột từ một bảng và đặt những cột đó vào các bảng mới riêng biệt. Mỗi mảnh chứa cả hàng và cột riêng biệt, với dữ liệu hoàn toàn độc lập từ phân vùng này đến phân vùng khác.

Ví dụ, trong một ứng dụng mạng xã hội như Twitter:
- Hồ sơ người dùng có thể ở trên một mảnh
- Thông tin người theo dõi ở mảnh thứ hai
- Các tweet ở mảnh thứ ba

**Ưu điểm của Phân Mảnh Theo Chiều Dọc:**
- Cải thiện hiệu suất truy vấn khi mỗi mảnh tập trung vào một tập con cụ thể của các cột
- Đơn giản hóa truy vấn cho các tập cột cụ thể
- Giảm yêu cầu I/O cho các truy vấn chỉ cần các cột cụ thể

**Nhược điểm của Phân Mảnh Theo Chiều Dọc:**
- Tiềm ẩn điểm nóng nếu một số mảnh chứa các cột được truy cập nhiều
- Thách thức với các thay đổi lược đồ qua nhiều mảnh
- Các truy vấn phức tạp hơn khi cần dữ liệu từ nhiều mảnh

### 4. Phân Mảnh Dựa Trên Thư Mục

Trong phân mảnh dựa trên thư mục, chúng ta tạo và duy trì một dịch vụ tra cứu hoặc bảng tra cứu ánh xạ dữ liệu đến mảnh thích hợp. Dịch vụ tra cứu theo dõi xem mảnh cơ sở dữ liệu nào chứa dữ liệu nào.

Khi một khách hàng cần truy cập dữ liệu:
1. Nó truy vấn dịch vụ tra cứu để tìm mảnh thích hợp
2. Sau khi nhận được vị trí mảnh, nó truy vấn mảnh cụ thể đó

**Ưu điểm của Phân Mảnh Dựa Trên Thư Mục:**
- Phân phối dữ liệu linh hoạt có thể được quản lý động
- Định tuyến truy vấn hiệu quả
- Khả năng mở rộng động mà không yêu cầu thay đổi logic ứng dụng

**Nhược điểm của Phân Mảnh Dựa Trên Thư Mục:**
- Thư mục trung tâm đại diện cho một điểm lỗi đơn lẻ
- Tăng độ trễ do bước tra cứu bổ sung
- Phức tạp hơn để triển khai và duy trì

## Tối Ưu Hóa Phân Mảnh Cơ Sở Dữ Liệu cho Phân Phối Dữ Liệu Đồng Đều

Để đảm bảo hiệu suất tối ưu và tránh các điểm nóng trong hệ thống cơ sở dữ liệu đã phân mảnh, hãy xem xét các kỹ thuật tối ưu hóa sau:

1. **Sử Dụng Băm Nhất Quán**: Điều này phân phối dữ liệu đồng đều hơn qua các mảnh và giảm thiểu chuyển động dữ liệu khi thêm hoặc xóa mảnh.

2. **Chọn Khóa Phân Mảnh Tốt**: Chọn khóa phân mảnh phân phối dữ liệu đồng đều và phù hợp với mẫu truy vấn phổ biến nhất của bạn.

3. **Giám Sát và Cân Bằng Lại**: Thường xuyên giám sát việc sử dụng và hiệu suất mảnh, cân bằng lại dữ liệu qua các mảnh khi cần thiết.

4. **Xem Xét Khóa Phân Mảnh Tổng Hợp**: Sử dụng nhiều cột làm khóa phân mảnh có thể cung cấp mẫu phân phối tốt hơn.

5. **Phân Chia Mảnh Trước**: Nếu bạn dự đoán sự phát triển, hãy phân chia trước các mảnh của bạn để thích ứng với dữ liệu trong tương lai mà không cần nỗ lực phân phối lại lớn.

## Các Lựa Chọn Thay Thế cho Phân Mảnh Cơ Sở Dữ Liệu

Mặc dù phân mảnh là một chiến lược mở rộng hiệu quả, các phương pháp khác có thể phù hợp hơn tùy thuộc vào yêu cầu cụ thể của bạn:

1. **Mở Rộng Theo Chiều Dọc**: Thêm nhiều tài nguyên (CPU, RAM, lưu trữ) vào máy chủ cơ sở dữ liệu hiện tại của bạn.

2. **Sao Chép**: Tạo bản sao của cơ sở dữ liệu của bạn trên nhiều máy chủ để cải thiện hiệu suất đọc và khả năng khả dụng.

3. **Phân Vùng**: Chia dữ liệu trong cùng một máy chủ thành các phần nhỏ hơn để cải thiện hiệu suất truy vấn.

4. **Bộ Nhớ Đệm**: Lưu trữ dữ liệu được truy cập thường xuyên trong hệ thống bộ nhớ đệm như Redis hoặc Memcached để giảm tải cơ sở dữ liệu.

5. **CDNs**: Sử dụng Mạng Phân Phối Nội Dung cho khối lượng công việc đọc nặng để giảm tải truy cập dữ liệu từ cơ sở dữ liệu chính của bạn.

## Ưu Điểm của Phân Mảnh trong Thiết Kế Hệ Thống

1. **Nâng Cao Hiệu Suất**: Bằng cách phân phối tải qua nhiều máy chủ, phân mảnh có thể cải thiện đáng kể hiệu suất cơ sở dữ liệu.

2. **Cải Thiện Khả Năng Mở Rộng**: Phân mảnh cho phép mở rộng theo chiều ngang bằng cách thêm nhiều máy chủ cơ sở dữ liệu khi khối lượng dữ liệu tăng lên.

3. **Tăng Khả Năng Khả Dụng**: Nếu một mảnh bị lỗi, chỉ một phần của dữ liệu trở nên không khả dụng, trong khi phần còn lại của hệ thống tiếp tục hoạt động.

4. **Sử Dụng Tài Nguyên Tốt Hơn**: Phân mảnh cho phép sử dụng tài nguyên hiệu quả hơn bằng cách phân phối xử lý dữ liệu qua nhiều máy.

5. **Phân Phối Địa Lý**: Các mảnh có thể được đặt ở các vị trí địa lý khác nhau để giảm độ trễ cho người dùng ở các khu vực đó.

## Nhược Điểm của Phân Mảnh trong Thiết Kế Hệ Thống

1. **Tăng Độ Phức Tạp**: Quản lý và duy trì nhiều mảnh phức tạp hơn so với làm việc với một cơ sở dữ liệu đơn lẻ.

2. **Thách Thức Cân Bằng Lại**: Nếu phân phối dữ liệu trở nên không đều, việc cân bằng lại các mảnh có thể khó khăn và tốn thời gian.

3. **Truy Vấn Qua Nhiều Mảnh**: Các truy vấn cần dữ liệu từ nhiều mảnh có thể chậm hơn và phức tạp hơn để xử lý.

4. **Chi Phí Vận Hành**: Phân mảnh yêu cầu nhiều giám sát, sao lưu và bảo trì hơn, tăng chi phí vận hành.

5. **Tiềm Năng Mất Dữ Liệu**: Nếu một mảnh bị lỗi mà không có sao lưu thích hợp, có nguy cơ cao hơn mất dữ liệu được lưu trữ trên mảnh đó.

## Khi Nào Nên Sử Dụng Phân Mảnh Cơ Sở Dữ Liệu

Xem xét triển khai phân mảnh cơ sở dữ liệu khi:

1. Kích thước cơ sở dữ liệu của bạn vượt quá dung lượng của một máy chủ đơn lẻ
2. Khối lượng giao dịch quá cao cho một phiên bản cơ sở dữ liệu đơn lẻ
3. Các thao tác ghi đang tạo ra nút thắt cổ chai hiệu suất
4. Bạn cần mở rộng vượt quá giới hạn mở rộng theo chiều dọc của cơ sở hạ tầng của bạn
5. Bạn cần cải thiện hiệu suất cho các khu vực địa lý cụ thể

## Các Cân Nhắc Khi Triển Khai

Khi triển khai phân mảnh cơ sở dữ liệu, hãy xem xét các yếu tố chính sau:

1. **Lựa Chọn Khóa Phân Mảnh**: Việc lựa chọn khóa phân mảnh là quan trọng, vì nó quyết định cách dữ liệu được phân phối qua các mảnh.

2. **Định Tuyến Truy Vấn**: Phát triển cơ chế mạnh mẽ để định tuyến truy vấn đến (các) mảnh thích hợp.

3. **Thao Tác Qua Nhiều Mảnh**: Thiết kế chiến lược để xử lý các truy vấn trải dài trên nhiều mảnh.

4. **Thay Đổi Lược Đồ**: Lập kế hoạch cho cách thay đổi lược đồ sẽ được lan truyền qua tất cả các mảnh.

5. **Giám Sát và Quản Lý**: Triển khai giám sát toàn diện để xác định vấn đề hiệu suất và mất cân bằng.

## Kết Luận

Phân mảnh cơ sở dữ liệu là một kỹ thuật mạnh mẽ để mở rộng cơ sở dữ liệu theo chiều ngang khi dung lượng máy chủ đơn lẻ không còn đủ. Mặc dù nó đưa vào độ phức tạp về phân phối dữ liệu, định tuyến truy vấn và quản lý, phân mảnh mang lại lợi ích đáng kể về hiệu suất, khả năng mở rộng và tính khả dụng cho các ứng dụng quy mô lớn.

Chìa khóa để phân mảnh thành công nằm ở việc chọn chiến lược phân mảnh phù hợp, chọn khóa phân mảnh thích hợp và triển khai cơ chế hiệu quả cho định tuyến truy vấn và các thao tác qua nhiều mảnh. Khi được triển khai đúng cách, phân mảnh có thể giúp ứng dụng của bạn xử lý sự tăng trưởng lớn về khối lượng dữ liệu và lưu lượng người dùng trong khi vẫn duy trì hiệu suất và độ tin cậy.
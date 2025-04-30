# Availability in System Design

## What is Availability?

In system design, availability refers to the proportion of time that a system or service is operational and accessible for use. It is a critical aspect of designing reliable and resilient systems, especially in the context of online services, websites, cloud-based applications, and other mission-critical systems.

High availability is necessary for systems that need to run continuously since any disruption could lead to losses in money, reputational damage, or even safety hazards. Systems that usually demand high availability include cloud infrastructure, emergency response services, healthcare systems, e-commerce platforms, and banking apps.

## How is availability measured?

Availability is typically measured as a percentage of uptime over a specific period, often expressed in terms of "nines". For example:

- 99% availability (two nines): 3.65 days of downtime per year
- 99.9% availability (three nines): 8.76 hours of downtime per year
- 99.99% availability (four nines): 52.56 minutes of downtime per year
- 99.999% availability (five nines): 5.26 minutes of downtime per year
- 99.9999% availability (six nines): 31.5 seconds of downtime per year

The more "nines" in the availability percentage, the higher the level of reliability and the lower the amount of acceptable downtime.

## How to achieve high availability?

System designers implement various strategies and technologies to achieve high availability, such as:

1. **Redundancy**: Use redundant servers or components so that, in the event of a failure, another can take over without any problems. Data centers, networking, and hardware redundancy are a few examples of this.

2. **Load balancing**: Incoming requests are divided among several servers or resources to enhance system performance and fault tolerance while avoiding overload on any one part.

3. **Failover mechanisms**: Implementing automated processes to detect failures and switch to redundant systems without manual intervention.

4. **Distributed systems**: Spreading the system across multiple locations or regions to minimize the impact of localized failures like power outages or natural disasters.

5. **Data backups and replication**: Regularly backing up data and replicating it across multiple systems to prevent data loss in case of failures.

6. **Monitoring and alerts**: Using monitoring tools to detect issues before they cause service disruptions and implementing alert systems for quick response.

7. **Graceful degradation**: Designing systems to maintain core functionality even when some components fail.

## Importance of Availability in System Design

High availability is a critical consideration in system design for several reasons:

1. **Business continuity**: For businesses that rely on digital systems, downtime can lead to significant financial losses.

2. **User trust and satisfaction**: Systems that frequently experience downtime can lead to poor user experiences and loss of trust.

3. **Competitive advantage**: Higher availability rates can provide a competitive edge in industries where reliability is a key differentiator.

4. **Regulatory compliance**: In many industries, there are regulatory requirements or standards that mandate a minimum level of system availability. Failure to comply with these regulations can result in legal consequences, fines, or sanctions.

## Difference between High Availability and Fault Tolerance

While often used interchangeably, high availability and fault tolerance have distinct meanings:

| Aspect | High Availability | Fault Tolerance |
|--------|-------------------|-----------------|
| **Definition** | System's ability to operate continuously without failure for a desired period | System's ability to continue functioning properly in the presence of faults |
| **Focus** | Maximizes system uptime | Ensures continuous operation despite failures |
| **Recovery** | Quick recovery after failures | Continues operation without interruption during failures |
| **Use Cases** | Critical for systems that need to be accessible and operational at almost all times (e.g., e-commerce, banking) | Important in safety-critical systems, aerospace, healthcare, and other scenarios where system failure can lead to severe consequences |
| **Redundancy Level** | High availability may involve some redundancy, but it may not eliminate all single points of failure | Fault tolerance often requires a higher degree of redundancy to provide backup mechanisms for various components |

## Real-world Examples of High-Availability Systems

1. **Cloud Services**: Major providers like AWS, Azure, and Google Cloud offer multiple availability zones and regions to ensure continuous service.

2. **Banking Systems**: Financial institutions implement redundant data centers and real-time failover mechanisms to prevent service interruptions.

3. **E-commerce Platforms**: Online retailers maintain high availability especially during peak shopping seasons to prevent loss of sales.

4. **Healthcare Systems**: Patient monitoring and electronic health record systems often employ redundant infrastructure to ensure continuous operation.

5. **Telecommunications Networks**: Telecom providers implement redundant paths and equipment to maintain connectivity.

---

# Tính khả dụng trong Thiết kế Hệ thống

## Tính khả dụng là gì?

Trong thiết kế hệ thống, tính khả dụng đề cập đến tỷ lệ thời gian mà một hệ thống hoặc dịch vụ hoạt động và có thể truy cập được. Đây là một khía cạnh quan trọng của việc thiết kế các hệ thống đáng tin cậy và có khả năng phục hồi, đặc biệt là trong bối cảnh các dịch vụ trực tuyến, trang web, ứng dụng dựa trên đám mây và các hệ thống quan trọng khác.

Tính khả dụng cao là cần thiết cho các hệ thống cần hoạt động liên tục vì bất kỳ sự gián đoạn nào cũng có thể dẫn đến mất tiền, thiệt hại về uy tín, hoặc thậm chí là các mối nguy hiểm về an toàn. Các hệ thống thường đòi hỏi tính khả dụng cao bao gồm cơ sở hạ tầng đám mây, dịch vụ ứng phó khẩn cấp, hệ thống chăm sóc sức khỏe, nền tảng thương mại điện tử và các ứng dụng ngân hàng.

## Tính khả dụng được đo lường như thế nào?

Tính khả dụng thường được đo lường bằng tỷ lệ phần trăm thời gian hoạt động trong một khoảng thời gian cụ thể, thường được biểu thị bằng "số 9". Ví dụ:

- 99% khả dụng (hai số 9): 3,65 ngày dừng hoạt động mỗi năm
- 99,9% khả dụng (ba số 9): 8,76 giờ dừng hoạt động mỗi năm
- 99,99% khả dụng (bốn số 9): 52,56 phút dừng hoạt động mỗi năm
- 99,999% khả dụng (năm số 9): 5,26 phút dừng hoạt động mỗi năm
- 99,9999% khả dụng (sáu số 9): 31,5 giây dừng hoạt động mỗi năm

Càng nhiều "số 9" trong tỷ lệ khả dụng, mức độ đáng tin cậy càng cao và thời gian dừng hoạt động có thể chấp nhận được càng thấp.

## Làm thế nào để đạt được tính khả dụng cao?

Các nhà thiết kế hệ thống triển khai các chiến lược và công nghệ khác nhau để đạt được tính khả dụng cao, chẳng hạn như:

1. **Dự phòng**: Sử dụng máy chủ hoặc thành phần dự phòng để trong trường hợp xảy ra lỗi, thành phần khác có thể tiếp quản mà không gặp vấn đề gì. Trung tâm dữ liệu, mạng và dự phòng phần cứng là một vài ví dụ về điều này.

2. **Cân bằng tải**: Các yêu cầu đến được phân chia giữa nhiều máy chủ hoặc tài nguyên để tăng cường hiệu suất hệ thống và khả năng chịu lỗi đồng thời tránh quá tải trên bất kỳ phần nào.

3. **Cơ chế chuyển đổi dự phòng**: Triển khai các quy trình tự động để phát hiện lỗi và chuyển sang hệ thống dự phòng mà không cần can thiệp thủ công.

4. **Hệ thống phân tán**: Phân bố hệ thống trên nhiều vị trí hoặc khu vực để giảm thiểu tác động của các lỗi cục bộ như mất điện hoặc thảm họa tự nhiên.

5. **Sao lưu và sao chép dữ liệu**: Thường xuyên sao lưu dữ liệu và sao chép chúng trên nhiều hệ thống để ngăn chặn mất dữ liệu trong trường hợp có lỗi.

6. **Giám sát và cảnh báo**: Sử dụng công cụ giám sát để phát hiện vấn đề trước khi chúng gây ra gián đoạn dịch vụ và triển khai hệ thống cảnh báo để phản ứng nhanh chóng.

7. **Suy giảm nhẹ nhàng**: Thiết kế hệ thống để duy trì chức năng cốt lõi ngay cả khi một số thành phần gặp lỗi.

## Tầm quan trọng của Tính khả dụng trong Thiết kế Hệ thống

Tính khả dụng cao là một yếu tố quan trọng trong thiết kế hệ thống vì nhiều lý do:

1. **Tính liên tục kinh doanh**: Đối với các doanh nghiệp phụ thuộc vào hệ thống kỹ thuật số, thời gian ngừng hoạt động có thể dẫn đến tổn thất tài chính đáng kể.

2. **Niềm tin và sự hài lòng của người dùng**: Các hệ thống thường xuyên gặp thời gian ngừng hoạt động có thể dẫn đến trải nghiệm người dùng kém và mất lòng tin.

3. **Lợi thế cạnh tranh**: Tỷ lệ khả dụng cao hơn có thể mang lại lợi thế cạnh tranh trong các ngành mà độ tin cậy là yếu tố phân biệt quan trọng.

4. **Tuân thủ quy định**: Trong nhiều ngành công nghiệp, có các yêu cầu quy định hoặc tiêu chuẩn yêu cầu mức tối thiểu của tính khả dụng hệ thống. Không tuân thủ các quy định này có thể dẫn đến hậu quả pháp lý, tiền phạt hoặc trừng phạt.

## Sự khác biệt giữa Tính khả dụng cao và Khả năng chịu lỗi

Mặc dù thường được sử dụng thay thế cho nhau, tính khả dụng cao và khả năng chịu lỗi có ý nghĩa riêng biệt:

| Khía cạnh | Tính khả dụng cao | Khả năng chịu lỗi |
|--------|-------------------|-----------------|
| **Định nghĩa** | Khả năng của hệ thống hoạt động liên tục mà không có lỗi trong một khoảng thời gian mong muốn | Khả năng của hệ thống tiếp tục hoạt động đúng khi có lỗi |
| **Trọng tâm** | Tối đa hóa thời gian hoạt động của hệ thống | Đảm bảo hoạt động liên tục bất chấp các lỗi |
| **Phục hồi** | Phục hồi nhanh sau khi gặp lỗi | Tiếp tục hoạt động không bị gián đoạn khi có lỗi |
| **Trường hợp sử dụng** | Quan trọng đối với các hệ thống cần được truy cập và vận hành gần như mọi lúc (ví dụ: thương mại điện tử, ngân hàng) | Quan trọng trong các hệ thống quan trọng về an toàn, hàng không vũ trụ, chăm sóc sức khỏe và các kịch bản khác nơi lỗi hệ thống có thể dẫn đến hậu quả nghiêm trọng |
| **Mức độ dự phòng** | Tính khả dụng cao có thể bao gồm một số dự phòng, nhưng có thể không loại bỏ tất cả các điểm lỗi đơn | Khả năng chịu lỗi thường đòi hỏi mức độ dự phòng cao hơn để cung cấp cơ chế dự phòng cho các thành phần khác nhau |

## Ví dụ thực tế về Hệ thống có Tính khả dụng cao

1. **Dịch vụ Đám mây**: Các nhà cung cấp lớn như AWS, Azure và Google Cloud cung cấp nhiều vùng và khu vực khả dụng để đảm bảo dịch vụ liên tục.

2. **Hệ thống Ngân hàng**: Các tổ chức tài chính triển khai trung tâm dữ liệu dự phòng và cơ chế chuyển đổi dự phòng thời gian thực để ngăn chặn gián đoạn dịch vụ.

3. **Nền tảng Thương mại điện tử**: Các nhà bán lẻ trực tuyến duy trì tính khả dụng cao đặc biệt trong mùa mua sắm cao điểm để ngăn chặn mất doanh số.

4. **Hệ thống Y tế**: Hệ thống theo dõi bệnh nhân và hệ thống hồ sơ sức khỏe điện tử thường sử dụng cơ sở hạ tầng dự phòng để đảm bảo hoạt động liên tục.

5. **Mạng Viễn thông**: Các nhà cung cấp viễn thông triển khai các đường dẫn và thiết bị dự phòng để duy trì kết nối.
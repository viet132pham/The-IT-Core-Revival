# Starvation và Aging trong Hệ điều hành

## Starvation là gì?
Starvation (tắc nghẽn vô thời hạn) là một hiện tượng xảy ra trong thuật toán lập lịch ưu tiên, trong đó một tiến trình có mức ưu tiên thấp có thể chờ đợi vô thời hạn để được cấp CPU hoặc tài nguyên.

Ví dụ: Nếu trong một hệ thống có nhiều tiến trình với mức ưu tiên cao liên tục đến trước, một tiến trình có mức ưu tiên thấp sẽ không bao giờ được thực thi.

### Nguyên nhân gây ra Starvation
1. **Tài nguyên khan hiếm**: Khi có quá nhiều tiến trình tranh giành tài nguyên, những tiến trình có mức ưu tiên thấp sẽ không được cấp phát tài nguyên kịp thời.
2. **Tiến trình ưu tiên cao chiếm dụng CPU**: Nếu một hệ thống sử dụng thuật toán lập lịch ưu tiên mà không có cơ chế kiểm soát, các tiến trình có mức ưu tiên cao liên tục được cấp CPU, khiến tiến trình có mức ưu tiên thấp không bao giờ được thực thi.
3. **Cơ chế chọn tiến trình không công bằng**: Nếu hệ điều hành chọn tiến trình ngẫu nhiên mà không có chính sách công bằng, một số tiến trình có thể bị bỏ qua vô thời hạn.
4. **Quyết định cấp phát tài nguyên kém**: Nếu hệ điều hành không có chiến lược hợp lý trong việc cấp phát tài nguyên, một số tiến trình có thể bị bỏ rơi trong hàng đợi chờ đợi.

## Cách kiểm soát Starvation
1. **Quản lý tài nguyên công bằng**: Hệ điều hành có thể sử dụng một trình quản lý tài nguyên để đảm bảo rằng tài nguyên được phân phối một cách công bằng.
2. **Tránh lựa chọn ngẫu nhiên**: Khi cấp phát tài nguyên hoặc CPU, hệ điều hành không nên chọn tiến trình một cách ngẫu nhiên mà nên có chiến lược đảm bảo công bằng.
3. **Sử dụng cơ chế Aging**: Aging là một phương pháp giúp tăng dần mức ưu tiên của các tiến trình chờ đợi lâu để đảm bảo rằng chúng không bị bỏ rơi vô thời hạn.

## Sự khác biệt giữa Deadlock và Starvation
| Tiêu chí  | Deadlock | Starvation |
|-----------|----------|------------|
| Định nghĩa | Xảy ra khi không có tiến trình nào trong tập tiến trình có thể tiếp tục thực thi do bị giữ tài nguyên bởi tiến trình khác | Xảy ra khi một tiến trình chờ vô thời hạn vì không được cấp tài nguyên |
| Tên gọi khác | Chờ đợi vòng tròn (Circular Waiting) | Lived Lock |
| Ảnh hưởng | Không tiến trình nào có thể tiếp tục | Chỉ có tiến trình ưu tiên thấp bị ảnh hưởng, các tiến trình khác vẫn tiếp tục |

---

## Aging là gì?
Aging là một kỹ thuật giúp tăng dần mức ưu tiên của các tiến trình chờ đợi lâu trong hệ thống, giúp ngăn chặn tình trạng Starvation. Khi một tiến trình chờ đợi càng lâu, mức ưu tiên của nó sẽ dần được tăng lên để đảm bảo rằng nó sẽ được thực thi sau một khoảng thời gian nhất định.

Ví dụ: Nếu hệ thống có mức ưu tiên từ 127 (thấp nhất) đến 0 (cao nhất), chúng ta có thể tăng mức ưu tiên của một tiến trình chờ đợi mỗi 15 phút. Như vậy, một tiến trình có mức ưu tiên ban đầu là 127 sẽ mất tối đa 32 giờ để trở thành tiến trình có mức ưu tiên cao nhất (0) và được thực thi.

### Ứng dụng của Aging
1. **Tránh tình trạng Starvation**: Aging đảm bảo rằng các tiến trình có mức ưu tiên thấp cũng sẽ được thực thi sau một khoảng thời gian chờ đợi.
2. **Phân bổ tài nguyên công bằng**: Các tiến trình sẽ có cơ hội sử dụng CPU và tài nguyên một cách công bằng.
3. **Cải thiện hiệu suất hệ thống**: Nhờ vào Aging, các tiến trình không bị chờ đợi vô thời hạn, giúp hệ thống hoạt động hiệu quả hơn.
4. **Tránh đảo ngược mức ưu tiên (Priority Inversion)**: Priority Inversion xảy ra khi một tiến trình có mức ưu tiên thấp giữ tài nguyên mà một tiến trình ưu tiên cao cần. Aging giúp giảm thiểu tình trạng này.

### Hạn chế của Aging
1. **Tăng độ phức tạp của thuật toán**: Hệ điều hành cần theo dõi thời gian chờ đợi của từng tiến trình và điều chỉnh mức ưu tiên tương ứng.
2. **Chi phí quản lý cao**: Việc cập nhật mức ưu tiên liên tục có thể gây ra chi phí vận hành cao.
3. **Hành vi khó dự đoán**: Nếu tốc độ tăng ưu tiên không hợp lý, có thể gây ra tình trạng ưu tiên thay đổi quá nhanh hoặc quá chậm, làm giảm hiệu quả của hệ thống.
4. **Có thể gây bất công với tiến trình mới**: Aging có thể ưu tiên các tiến trình đã chờ đợi lâu hơn, dẫn đến việc tiến trình mới bị bỏ rơi.

## Kết luận
Starvation là một vấn đề quan trọng trong lập lịch tiến trình của hệ điều hành, đặc biệt là trong các thuật toán lập lịch ưu tiên. Để giải quyết vấn đề này, kỹ thuật Aging được sử dụng để đảm bảo rằng tất cả các tiến trình đều có cơ hội được thực thi. Tuy nhiên, việc triển khai Aging cần phải được cân nhắc cẩn thận để tránh ảnh hưởng đến hiệu suất hệ thống.


# Difference between Concurrency and Parallelism

## What is Concurrency?

Concurrency relates to an application that is processing more than one task at the same time. Concurrency is an approach that is used for decreasing the response time of the system by using a single processing unit. Concurrency creates the illusion of parallelism; however, actually the chunks of a task aren't parallelly processed, but inside the application, there are more than one task being processed at a time. It doesn't fully end one task before it begins the next one.

Concurrency is achieved through the interleaving operation of processes on the central processing unit (CPU) or in other words by context switching. That's why it's like parallel processing. It increases the amount of work finished at a time.

![Concurrency](https://media.geeksforgeeks.org/wp-content/uploads/20190702120716/concurrency.jpg)

In the above figure, we can see that there are multiple tasks making progress at the same time. This figure shows concurrency because concurrency is the technique that deals with a lot of things at one time.

## What is Parallelism?

Parallelism is related to an application where tasks are divided into smaller sub-tasks that are processed simultaneously or in parallel. It is used to increase the throughput and computational speed of the system by using multiple processors. It enables single sequential CPUs to do a lot of things "seemingly" simultaneously.

Parallelism leads to overlapping of central processing units and input-output tasks in one process with the central processing unit and input-output tasks of another process. Whereas in concurrency, the speed is increased by overlapping the input-output activities of one process with the CPU process of another process.

![Parallelism](https://media.geeksforgeeks.org/wp-content/uploads/20190702120715/parallelism.jpg)

In the above figure, we can see that the tasks are divided into smaller sub-tasks that are processing simultaneously or in parallel. This figure shows parallelism, the technique that runs threads simultaneously.

## Differences between Concurrency and Parallelism

| S.NO | Concurrency | Parallelism |
|------|-------------|-------------|
| 1 | Concurrency is the task of running and managing the multiple computations at the same time. | Parallelism is the task of running multiple computations simultaneously. |
| 2 | Concurrency is achieved through the interleaving operation of processes on the central processing unit (CPU) or in other words by context switching. | Parallelism is achieved through multiple central processing units (CPUs). |
| 3 | Concurrency can be done by using a single processing unit. | Parallelism can't be done by using a single processing unit; it needs multiple processing units. |
| 4 | Concurrency increases the amount of work finished at a time. | Parallelism improves the throughput and computational speed of the system. |
| 5 | Concurrency deals with a lot of things simultaneously. | Parallelism does a lot of things simultaneously. |
| 6 | Concurrency is the non-deterministic control flow approach. | Parallelism is the deterministic control flow approach. |
| 7 | In concurrency debugging is very hard. | In parallelism debugging is also hard but simpler than concurrency. |

## How Concurrency Works

In a concurrent system, multiple tasks can start, run, and complete in overlapping time periods. It doesn't necessarily mean they'll ever both be running at the same instant. For example, a web server may handle multiple requests for the same resource by beginning to process the first request, and then, while waiting for an I/O operation to complete, processing the second request. When the I/O operation for the first request completes, the server will switch back to processing it. This is concurrency, not parallelism.

### Key Characteristics of Concurrency:

1. **Interleaving Execution**: Tasks are executed in interleaved fashion where CPU switches between tasks rather than executing multiple tasks simultaneously.

2. **Single Core Usage**: Can be achieved on a single processor core through context switching.

3. **Dealing with Multiple Tasks**: Managing multiple tasks at once without necessarily executing them simultaneously.

4. **Enhanced Responsiveness**: Improves system responsiveness by enabling the CPU to work on other tasks when one task is waiting (e.g., for I/O operations).

5. **Use Case Examples**: Web servers handling multiple client requests, user interfaces remaining responsive while background tasks execute.

## How Parallelism Works

In parallel computing, multiple processors or cores execute tasks simultaneously. The tasks are broken down into sub-tasks, and each processor works on its assigned sub-task at the same time. This approach significantly increases the system's computational power and processing speed.

### Key Characteristics of Parallelism:

1. **Simultaneous Execution**: Multiple tasks (or parts of tasks) execute at literally the same time on different processors.

2. **Multiple Core Requirement**: Requires multiple processor cores or separate physical machines.

3. **Task Division**: Tasks are typically divided into independent sub-tasks that can be processed in parallel.

4. **Increased Throughput**: Significantly improves processing throughput and computational speed.

5. **Use Case Examples**: Large-scale data processing, scientific simulations, graphics rendering, and machine learning applications.

## Real-world Applications

### Concurrency Applications:
- Web servers handling multiple client requests
- Operating systems running multiple programs
- User interfaces that remain responsive while processing
- Database management systems handling multiple transactions

### Parallelism Applications:
- Big data processing with frameworks like Hadoop or Spark
- Graphics processing in video games and 3D rendering
- Scientific simulations (weather models, physics simulations)
- Machine learning and artificial intelligence computations
- Image and video processing

## Choosing Between Concurrency and Parallelism

When designing a system, it's important to understand when to use concurrency and when to use parallelism:

### Choose Concurrency When:
- You have I/O-bound tasks that spend time waiting
- You need to maintain responsiveness in an application
- You have a single CPU/core available
- You need to handle many independent tasks

### Choose Parallelism When:
- You have CPU-intensive tasks
- You need to minimize processing time
- You have multiple CPUs/cores available
- You can divide tasks into independent chunks

In many modern systems, both concurrency and parallelism are used together to maximize efficiency and performance. For example, web servers may use concurrency to handle multiple connections while also using parallelism across multiple CPU cores to process requests faster.

---

# Sự khác biệt giữa Xử lý đồng thời và Xử lý song song

## Xử lý đồng thời (Concurrency) là gì?

Xử lý đồng thời liên quan đến một ứng dụng đang xử lý nhiều tác vụ cùng một lúc. Xử lý đồng thời là một cách tiếp cận được sử dụng để giảm thời gian phản hồi của hệ thống bằng cách sử dụng một đơn vị xử lý duy nhất. Xử lý đồng thời tạo ra ảo giác về xử lý song song; tuy nhiên, thực tế các phần của một tác vụ không được xử lý song song, nhưng bên trong ứng dụng, có nhiều hơn một tác vụ đang được xử lý tại một thời điểm. Nó không kết thúc hoàn toàn một tác vụ trước khi bắt đầu tác vụ tiếp theo.

Xử lý đồng thời đạt được thông qua hoạt động xen kẽ của các quy trình trên đơn vị xử lý trung tâm (CPU) hoặc nói cách khác bằng chuyển đổi ngữ cảnh. Đó là lý do tại sao nó giống như xử lý song song. Nó tăng lượng công việc được hoàn thành tại một thời điểm.

![Concurrency](https://media.geeksforgeeks.org/wp-content/uploads/20190702120716/concurrency.jpg)

Trong hình trên, chúng ta có thể thấy rằng có nhiều tác vụ đang tiến triển cùng một lúc. Hình này thể hiện xử lý đồng thời vì xử lý đồng thời là kỹ thuật xử lý nhiều việc cùng một lúc.

## Xử lý song song (Parallelism) là gì?

Xử lý song song liên quan đến một ứng dụng trong đó các tác vụ được chia thành các tác vụ con nhỏ hơn được xử lý đồng thời hoặc song song. Nó được sử dụng để tăng thông lượng và tốc độ tính toán của hệ thống bằng cách sử dụng nhiều bộ xử lý. Nó cho phép các CPU tuần tự đơn lẻ thực hiện nhiều việc "dường như" đồng thời.

Xử lý song song dẫn đến việc chồng chéo các đơn vị xử lý trung tâm và các tác vụ đầu vào-đầu ra trong một quy trình với đơn vị xử lý trung tâm và các tác vụ đầu vào-đầu ra của quy trình khác. Trong khi đó, trong xử lý đồng thời, tốc độ được tăng lên bằng cách chồng chéo các hoạt động đầu vào-đầu ra của một quy trình với quy trình CPU của quy trình khác.

![Parallelism](https://media.geeksforgeeks.org/wp-content/uploads/20190702120715/parallelism.jpg)

Trong hình trên, chúng ta có thể thấy rằng các tác vụ được chia thành các tác vụ con nhỏ hơn đang xử lý đồng thời hoặc song song. Hình này thể hiện xử lý song song, kỹ thuật chạy các luồng đồng thời.

## Sự khác biệt giữa Xử lý đồng thời và Xử lý song song

| STT | Xử lý đồng thời (Concurrency) | Xử lý song song (Parallelism) |
|-----|----------------------------|-------------------------|
| 1 | Xử lý đồng thời là nhiệm vụ chạy và quản lý nhiều phép tính cùng một lúc. | Xử lý song song là nhiệm vụ chạy nhiều phép tính đồng thời. |
| 2 | Xử lý đồng thời đạt được thông qua hoạt động xen kẽ của các quy trình trên đơn vị xử lý trung tâm (CPU) hoặc nói cách khác bằng chuyển đổi ngữ cảnh. | Xử lý song song đạt được thông qua nhiều đơn vị xử lý trung tâm (CPU). |
| 3 | Xử lý đồng thời có thể được thực hiện bằng cách sử dụng một đơn vị xử lý duy nhất. | Xử lý song song không thể được thực hiện bằng cách sử dụng một đơn vị xử lý duy nhất; nó cần nhiều đơn vị xử lý. |
| 4 | Xử lý đồng thời tăng lượng công việc được hoàn thành tại một thời điểm. | Xử lý song song cải thiện thông lượng và tốc độ tính toán của hệ thống. |
| 5 | Xử lý đồng thời xử lý nhiều việc đồng thời. | Xử lý song song thực hiện nhiều việc đồng thời. |
| 6 | Xử lý đồng thời là cách tiếp cận luồng điều khiển không xác định. | Xử lý song song là cách tiếp cận luồng điều khiển xác định. |
| 7 | Trong xử lý đồng thời, việc gỡ lỗi rất khó khăn. | Trong xử lý song song, việc gỡ lỗi cũng khó nhưng đơn giản hơn so với xử lý đồng thời. |

## Cách thức hoạt động của Xử lý đồng thời

Trong một hệ thống xử lý đồng thời, nhiều tác vụ có thể bắt đầu, chạy và hoàn thành trong các khoảng thời gian chồng chéo. Điều đó không nhất thiết có nghĩa là cả hai sẽ chạy cùng một lúc. Ví dụ, một máy chủ web có thể xử lý nhiều yêu cầu cho cùng một tài nguyên bằng cách bắt đầu xử lý yêu cầu đầu tiên, và sau đó, trong khi chờ đợi một hoạt động I/O hoàn thành, nó xử lý yêu cầu thứ hai. Khi hoạt động I/O cho yêu cầu đầu tiên hoàn thành, máy chủ sẽ chuyển trở lại xử lý nó. Đây là xử lý đồng thời, không phải xử lý song song.

### Đặc điểm chính của Xử lý đồng thời:

1. **Thực thi xen kẽ**: Các tác vụ được thực hiện theo cách xen kẽ trong đó CPU chuyển đổi giữa các tác vụ thay vì thực thi nhiều tác vụ đồng thời.

2. **Sử dụng đơn nhân**: Có thể đạt được trên một nhân xử lý duy nhất thông qua chuyển đổi ngữ cảnh.

3. **Xử lý nhiều tác vụ**: Quản lý nhiều tác vụ cùng một lúc mà không nhất thiết phải thực thi chúng đồng thời.

4. **Tăng khả năng phản hồi**: Cải thiện khả năng phản hồi của hệ thống bằng cách cho phép CPU làm việc trên các tác vụ khác khi một tác vụ đang chờ đợi (ví dụ, cho các hoạt động I/O).

5. **Ví dụ về trường hợp sử dụng**: Máy chủ web xử lý nhiều yêu cầu của khách hàng, giao diện người dùng vẫn phản hồi trong khi các tác vụ nền thực thi.

## Cách thức hoạt động của Xử lý song song

Trong tính toán song song, nhiều bộ xử lý hoặc nhân thực thi các tác vụ đồng thời. Các tác vụ được chia thành các tác vụ con, và mỗi bộ xử lý làm việc trên tác vụ con được giao cùng một lúc. Cách tiếp cận này làm tăng đáng kể sức mạnh tính toán và tốc độ xử lý của hệ thống.

### Đặc điểm chính của Xử lý song song:

1. **Thực thi đồng thời**: Nhiều tác vụ (hoặc các phần của tác vụ) thực thi chữ nghĩa cùng lúc trên các bộ xử lý khác nhau.

2. **Yêu cầu đa nhân**: Đòi hỏi nhiều nhân xử lý hoặc các máy vật lý riêng biệt.

3. **Phân chia tác vụ**: Các tác vụ thường được chia thành các tác vụ con độc lập có thể được xử lý song song.

4. **Tăng thông lượng**: Cải thiện đáng kể thông lượng xử lý và tốc độ tính toán.

5. **Ví dụ về trường hợp sử dụng**: Xử lý dữ liệu quy mô lớn, mô phỏng khoa học, kết xuất đồ họa và các ứng dụng học máy.

## Ứng dụng trong thực tế

### Ứng dụng của Xử lý đồng thời:
- Máy chủ web xử lý nhiều yêu cầu của khách hàng
- Hệ điều hành chạy nhiều chương trình
- Giao diện người dùng vẫn phản hồi trong khi xử lý
- Hệ thống quản lý cơ sở dữ liệu xử lý nhiều giao dịch

### Ứng dụng của Xử lý song song:
- Xử lý dữ liệu lớn với các framework như Hadoop hoặc Spark
- Xử lý đồ họa trong trò chơi video và kết xuất 3D
- Mô phỏng khoa học (mô hình thời tiết, mô phỏng vật lý)
- Tính toán học máy và trí tuệ nhân tạo
- Xử lý hình ảnh và video

## Lựa chọn giữa Xử lý đồng thời và Xử lý song song

Khi thiết kế một hệ thống, điều quan trọng là hiểu khi nào nên sử dụng xử lý đồng thời và khi nào nên sử dụng xử lý song song:

### Chọn Xử lý đồng thời khi:
- Bạn có các tác vụ bị giới hạn bởi I/O và dành thời gian chờ đợi
- Bạn cần duy trì khả năng phản hồi trong một ứng dụng
- Bạn có một CPU/nhân duy nhất
- Bạn cần xử lý nhiều tác vụ độc lập

### Chọn Xử lý song song khi:
- Bạn có các tác vụ đòi hỏi nhiều tài nguyên CPU
- Bạn cần giảm thiểu thời gian xử lý
- Bạn có nhiều CPU/nhân xử lý
- Bạn có thể chia các tác vụ thành các phần độc lập

Trong nhiều hệ thống hiện đại, cả xử lý đồng thời và xử lý song song được sử dụng cùng nhau để tối đa hóa hiệu quả và hiệu suất. Ví dụ, máy chủ web có thể sử dụng xử lý đồng thời để xử lý nhiều kết nối trong khi cũng sử dụng xử lý song song trên nhiều nhân CPU để xử lý các yêu cầu nhanh hơn.
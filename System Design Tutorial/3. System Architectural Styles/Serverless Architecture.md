## 🌐 English Version

### What is Serverless Architecture?

Serverless architecture is a cloud-computing execution model where the cloud provider dynamically manages the infrastructure. Developers only focus on writing code (functions), and the cloud handles provisioning, scaling, and maintaining servers.

Despite the name, **servers are still involved**, but developers do not have to manage them.

### Key Concepts

- **FaaS (Function-as-a-Service):** Developers deploy single-purpose functions triggered by events.
- **Event-Driven:** Functions are triggered by actions like file uploads, API calls, or database changes.
- **Stateless:** Functions do not retain state between invocations.

### Common Cloud Providers

- **AWS Lambda**
- **Google Cloud Functions**
- **Azure Functions**
- **IBM Cloud Functions**

### Benefits

- ✅ No server management
- ✅ Auto-scaling
- ✅ Pay-per-use (you only pay for execution time)
- ✅ Faster time to market

### Challenges

- ❌ Cold starts
- ❌ Vendor lock-in
- ❌ Debugging and monitoring complexity
- ❌ Stateless nature requires external services for state

### Example: Image Processing in E-commerce

1. User uploads a product image.
2. The image is stored in a Cloud Storage bucket.
3. A Cloud Function is triggered to:
   - Resize the image
   - Add a watermark
   - Store it in another folder
4. System notifies the backend that processing is complete.

---

## 🌏 Phiên bản Tiếng Việt

### Kiến trúc Serverless là gì?

Serverless là một mô hình điện toán đám mây nơi **nhà cung cấp dịch vụ chịu trách nhiệm hoàn toàn về máy chủ**, còn lập trình viên chỉ cần viết **code xử lý (function)**.

Mặc dù gọi là “không máy chủ”, thực tế **vẫn có máy chủ**, nhưng bạn không phải quản lý nó.

### Khái niệm chính

- **FaaS (Function-as-a-Service):** Bạn chỉ cần deploy các hàm nhỏ, chạy khi có sự kiện xảy ra.
- **Hướng sự kiện:** Các hàm sẽ được kích hoạt khi có sự kiện như upload file, gọi API, hoặc thay đổi trong DB.
- **Stateless:** Mỗi lần gọi function là một lần mới, không nhớ trạng thái cũ.

### Các nhà cung cấp phổ biến

- **AWS Lambda**
- **Google Cloud Functions**
- **Azure Functions**
- **IBM Cloud Functions**

### Ưu điểm

- ✅ Không cần quản lý server
- ✅ Tự động mở rộng (scaling)
- ✅ Chỉ trả tiền khi dùng
- ✅ Triển khai nhanh, linh hoạt

### Thách thức

- ❌ Độ trễ khởi động (cold start)
- ❌ Khó khăn khi chuyển đổi nhà cung cấp (vendor lock-in)
- ❌ Khó debug, khó theo dõi
- ❌ Cần dịch vụ khác để lưu trạng thái

### Ví dụ: Xử lý ảnh sản phẩm trong Thương mại điện tử

1. Người dùng upload ảnh sản phẩm.
2. Ảnh được lưu lên Google Cloud Storage.
3. Cloud Function được kích hoạt để:
   - Resize ảnh
   - Đóng watermark
   - Lưu ảnh đã xử lý vào thư mục khác
4. Hệ thống gửi thông báo về backend.

---

📌 Serverless không thay thế hoàn toàn backend truyền thống, nhưng là giải pháp **nhẹ, linh hoạt, và tiết kiệm chi phí** cho nhiều bài toán hiện đại như xử lý ảnh, gửi email, logging, hoặc tích hợp với IoT.


   - Tập trung vào logic code
   - Không quản lý hạ tầng
   - Triển khai nhanh chóng

3. **Tính năng tích hợp sẵn**
   - Tự động mở rộng
   - Tính sẵn sàng cao
   - Cập nhật bảo mật
   - Công cụ giám sát

### Thách thức

1. **Khởi động lạnh**
   - Độ trễ thực thi ban đầu
   - Ảnh hưởng hiệu suất
   - Tác động trải nghiệm người dùng

2. **Giới hạn tài nguyên**
   - Giới hạn thời gian chạy hàm
   - Giới hạn bộ nhớ
   - Giới hạn thực thi đồng thời

3. **Độ phức tạp phát triển**
   - Khó khăn trong debug
   - Hạn chế test cục bộ
   - Giám sát phức tạp 
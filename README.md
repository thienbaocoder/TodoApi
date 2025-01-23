# Minimal API với .NET 9

Minimal API trong ASP.NET Core được thiết kế để tạo ra các HTTP API nhẹ với ít phụ thuộc nhất, lý tưởng cho các microservices và ứng dụng yêu cầu triển khai API đơn giản nhưng mạnh mẽ.

## Tính năng

- **Nhẹ và Nhanh:** Ít phụ thuộc giúp tối ưu hiệu suất.
- **Đơn giản và Ngắn gọn:** Giảm bớt mã dư thừa so với MVC truyền thống.
- **Tích hợp DI:** Tích hợp dễ dàng với các dịch vụ ASP.NET Core.
- **Hỗ trợ Cơ sở dữ liệu In-Memory:** Thiết lập nhanh chóng với `Microsoft.EntityFrameworkCore.InMemory`.
- **Chức năng CRUD:** Hỗ trợ tạo, đọc, cập nhật và xóa các mục công việc.

## Thiết lập dự án

### 1. Tạo dự án API
1. Mở **Visual Studio 2022** và chọn **Create a new project**.
2. Chọn mẫu **ASP.NET Core Empty**.
3. Đặt tên dự án là `TodoApi` và chọn `.NET 9.0`.

### 2. Thêm các gói phụ thuộc
Cài đặt các gói NuGet cần thiết:

```shell
Install-Package Microsoft.EntityFrameworkCore.InMemory
Install-Package Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore
```

### 3. Định nghĩa Model và Database Context
Tạo model `Todo.cs` và context `TodoDb.cs` để quản lý dữ liệu.

### 4. Triển khai các API Endpoints
Thay thế nội dung của `Program.cs` bằng logic API để xử lý các thao tác CRUD.

## Các API Endpoint

| HTTP Method | Endpoint             | Mô tả                    | Request Body | Response Body |
|-------------|---------------------|--------------------------|--------------|---------------|
| GET         | /todoitems           | Lấy tất cả công việc      | None         | Mảng công việc|
| GET         | /todoitems/complete  | Lấy công việc đã hoàn thành| None         | Mảng công việc|
| GET         | /todoitems/{id}       | Lấy công việc theo ID     | None         | Công việc     |
| POST        | /todoitems            | Thêm công việc mới        | Công việc    | Công việc     |
| PUT         | /todoitems/{id}       | Cập nhật công việc        | Công việc    | None          |
| DELETE      | /todoitems/{id}       | Xóa công việc             | None         | None          |

## Chạy ứng dụng

1. Chạy dự án trong Visual Studio.
2. Chấp nhận bất kỳ cảnh báo tường lửa nào.
3. Ứng dụng sẽ khởi chạy trong trình duyệt với thông báo `Hello World!`.

## Kết quả đạt được

- **Phát triển API hiệu quả:** Mã tối giản với đầy đủ chức năng CRUD.
- **Tối ưu hiệu suất:** Nhẹ và xử lý nhanh chóng.
- **Bảo trì dễ dàng:** Cấu trúc đơn giản, dễ mở rộng.
- **Kiểm thử nhanh:** Có thể sử dụng Postman hoặc `Endpoints Explorer` trong VS Code để kiểm thử.

## Kiểm thử

Để kiểm thử API, gửi yêu cầu HTTP như sau:

```http
POST https://localhost:7169/todoitems
Content-Type: application/json

{
  "Name":"walk cat",
  "IsComplete":true
}
```
##Kết quả nhận được
![image](https://github.com/user-attachments/assets/57f0d52c-f9a9-4b0e-b14d-1c8ea3ba3f96)
![image](https://github.com/user-attachments/assets/dcfbb8f9-a96e-40a3-a064-8e548c1951f2)
![image](https://github.com/user-attachments/assets/0f52612a-b93a-47c3-b3c4-90e38da3eab8)





# Báo cáo Tiến độ Dự án - Tuần 3
**Dự án:** Hệ thống Quản lý Tài chính Cá nhân (FinFlow)
**Người thực hiện:** Bùi Duy Khánh
**Thời gian:** 20/04/2026 - 26/04/2026

---

## 1. Tổng quan công việc
Trong tuần này, trọng tâm của dự án là chuyển đổi nền tảng lưu trữ từ **MySQL** sang **SQL Server (MSSQL)** để phù hợp với môi trường triển khai Windows. Quá trình này gặp nhiều thử thách về mặt kỹ thuật liên quan đến cấu trúc dữ liệu và công cụ quản trị.

## 2. Các vấn đề kỹ thuật và giải pháp xử lý

### 2.1. Đồng bộ kiểu dữ liệu (Data Type Migration)
* **Vấn đề:** Các file Migration cũ từ MySQL chứa kiểu dữ liệu `longtext`, vốn không được SQL Server hỗ trợ.
* **Giải pháp:** * Xóa bỏ các thuộc tính `[Column(TypeName = "longtext")]` trong các file Models.
    * Thực hiện xóa sạch thư mục `Migrations` cũ để loại bỏ các lệnh SQL không tương thích.

### 2.2. Xử lý lỗi khóa ngoại và vòng lặp xóa (Cascade Cycles)
* **Vấn đề:** SQL Server chặn lệnh khởi tạo bảng `Transactions` do phát hiện nguy cơ lỗi vòng lặp xóa (Cycle/Multiple Cascade Paths) giữa `User`, `Wallet` và `Transaction`.
* **Giải pháp:** * Sử dụng Fluent API trong `ApplicationDbContext.cs`.
    * Cấu hình lại hành vi xóa: `.OnDelete(DeleteBehavior.NoAction)` cho các mối quan hệ gây xung đột.

### 2.3. Khắc phục lỗi công cụ Migration (EF Core Tools)
* **Vấn đề:** Lệnh `Add-Migration` không được nhận diện trong Package Manager Console do thiếu thư viện công cụ.
* **Giải pháp:** * Cài đặt lại gói `Microsoft.EntityFrameworkCore.Tools`.
    * Sử dụng thay thế bằng .NET CLI (`dotnet ef migrations add`) trong tab Developer PowerShell để đảm bảo tính ổn định.

### 2.4. Đồng bộ hóa Instance Database
* **Vấn đề:** Ứng dụng web chạy trên `SQLEXPRESS` nhưng công cụ quản lý (SSMS) lại kết nối vào `LocalDB` dẫn đến việc không thấy dữ liệu thực tế.
* **Giải pháp:** * Cập nhật `ConnectionStrings` trong `appsettings.json` trỏ chính xác về `Server=localhost\\SQLEXPRESS`.
    * Thực hiện lệnh `Update-Database` để đồng bộ cấu trúc bảng lên Server chính thức.

## 3. Kết quả đạt được
* [x] Chuyển đổi thành công Database sang SQL Server Express.
* [x] Khởi tạo đầy đủ cấu trúc bảng (Users, Wallets, Transactions, Budgets).
* [x] Xử lý thành công lỗi "Permission denied" trên GitHub bằng cách cấu hình `.gitignore` loại bỏ thư mục `.vs`.
* [x] Các chức năng cơ bản trên giao diện Web đã có thể đọc/ghi dữ liệu vào SQL Server.

## 4. Kế hoạch tuần 4
1. Hoàn thiện chức năng ghi chép giao dịch (Transaction Recording).
2. Xây dựng logic tính toán số dư ví tự động sau mỗi giao dịch.
3. Triển khai phần báo cáo chi tiêu theo danh mục (Category Statistics).

---
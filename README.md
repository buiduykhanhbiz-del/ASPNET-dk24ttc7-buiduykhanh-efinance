# 💰 EFinance - Quản Lý Tài Chính Cá Nhân

## 📌 Giới thiệu

**EFinance** là ứng dụng web giúp người dùng quản lý tài chính cá nhân, bao gồm quản lý ví, giao dịch, ngân sách và thống kê chi tiêu một cách trực quan và hiệu quả.

---

## 🎯 Chức năng chính

### 🔐 Xác thực người dùng

* Đăng ký tài khoản
* Đăng nhập / đăng xuất

📂 `Views/Account`

* Login.cshtml
* Register.cshtml

---

### 💼 Quản lý Ví

* Thêm ví mới
* Chỉnh sửa ví
* Xóa ví
* Xem danh sách ví

📂 `Views/Wallet`

* Index.cshtml
* Create.cshtml
* Edit.cshtml

---

### 💸 Quản lý Giao dịch

* Thêm giao dịch thu/chi
* Chỉnh sửa giao dịch
* Xóa giao dịch
* Thống kê giao dịch

📂 `Views/Transaction`

* Index.cshtml
* Create.cshtml
* Edit.cshtml
* Statistics.cshtml

---

### 📊 Thống kê

* Biểu đồ tròn (cơ cấu chi tiêu)
* Biểu đồ cột (thu vs chi)
* Tổng thu, tổng chi, tài sản

---

### 📅 Quản lý Ngân sách

* Tạo ngân sách theo danh mục
* Theo dõi chi tiêu
* Kiểm tra trạng thái ngân sách

📂 `Views/Budget`

* Index.cshtml
* Create.cshtml
* Edit.cshtml
* CheckStatus.cshtml

---

## 🗂️ Cấu trúc dự án

```
Views/
│
├── Account/
│   ├── Login.cshtml
│   └── Register.cshtml
│
├── Budget/
│   ├── Index.cshtml
│   ├── Create.cshtml
│   ├── Edit.cshtml
│   └── CheckStatus.cshtml
│
├── Transaction/
│   ├── Index.cshtml
│   ├── Create.cshtml
│   ├── Edit.cshtml
│   └── Statistics.cshtml
│
├── Wallet/
│   ├── Index.cshtml
│   ├── Create.cshtml
│   └── Edit.cshtml
│
├── Home/
│   └── Index.cshtml
│
└── Shared/
    ├── _Layout.cshtml
    └── _ValidationScriptsPartial.cshtml
```

---

## ⚙️ Công nghệ sử dụng

* ASP.NET Core MVC
* Entity Framework Core
* SQL Server
* Bootstrap 5
* Chart.js

---

## 🚀 Cách chạy dự án

### 1. Clone project

```bash
git clone https://github.com/buiduykhanhbiz-del/ASPNET-dk24ttc7-buiduykhanh-efinance.git
cd ASPNET-dk24ttc7-buiduykhanh-efinance
```

---

### 2. Cấu hình Database

* Mở file `appsettings.json`
* Chỉnh lại connection string:

```json
"DefaultConnection": "Server=localhost;Database=PersonalFinanceDB;Trusted_Connection=True;TrustServerCertificate=True;"
```

👉 Có thể thay:

* `localhost`
* `.`
* `localhost\\SQLEXPRESS`

---

### 3. Khởi tạo Database

⚠️ Chọn **1 trong 2 cách**

#### 🔹 Cách 1: Entity Framework (Khuyến nghị)

```bash
dotnet tool restore
dotnet ef migrations add InitialCreate
dotnet ef database update
```

---

#### 🔹 Cách 2: Import file SQL (nếu có)

1. Mở SQL Server Management Studio (SSMS)
2. Tạo database `PersonalFinanceDB`
3. Mở file `.sql`
4. Execute để chạy script

---

### 4. Chạy project

```bash
dotnet watch run
```

---

## 📸 Giao diện (Demo)

* Trang quản lý ví
* Trang thống kê
* Trang ngân sách

---

## 📅 Tiến độ thực hiện

| Tuần | Nội dung                 |
| ---- | ------------------------ |
| 1    | Thiết kế database        |
| 2    | CRUD ví                  |
| 3    | CRUD giao dịch           |
| 4    | Thống kê + biểu đồ       |
| 5    | Ngân sách                |
| 6    | Hoàn thiện UI & hệ thống |

---

## 👨‍🎓 Thông tin sinh viên

* Họ tên: Bùi Duy Khánh
* MSSV: 170124742
* Lớp: DK24TTC7
* Email: [khanhbd220801@tvu-onschool.edu.vn](mailto:khanhbd220801@tvu-onschool.edu.vn)

---

## 📌 Hướng phát triển

* Xuất báo cáo Excel
* Thông báo khi vượt ngân sách
* Hoàn thiện responsive cho mobile

---

## ⭐ Kết luận

Hệ thống giúp người dùng theo dõi và kiểm soát tài chính cá nhân một cách hiệu quả thông qua giao diện trực quan, dễ sử dụng và có khả năng mở rộng trong tương lai.

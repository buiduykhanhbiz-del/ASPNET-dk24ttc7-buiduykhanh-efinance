# 💰 EFinance - Quản Lý Tài Chính Cá Nhân

## 📌 Giới thiệu

**EFinance** là ứng dụng web giúp người dùng quản lý tài chính cá nhân, bao gồm ví, giao dịch, ngân sách và thống kê chi tiêu.

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

```id="tree1"
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

```bash id="clone2"
git clone https://github.com/buiduykhanhbiz-del/ASPNET-dk24ttc7-buiduykhanh-efinance.git
```

### 2. Cấu hình database

* Mở `appsettings.json`
* Chỉnh connection string thông tin mysql

### 3. Cập nhật database

```bash id="db2"
dotnet tool restore
dotnet ef database update --verbose
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 4. Chạy project

```bash id="run2"
dotnet wath run
```

---

## 📸 Giao diện (Demo)

* Trang ví
* Trang thống kê
* Trang ngân sách


---

## 📅 Tiến độ thực hiện

| Tuần | Nội dung           |
| ---- | ------------------ |
| 1    | Thiết kế database  |
| 2    | CRUD ví            |
| 3    | CRUD giao dịch     |
| 4    | Thống kê + biểu đồ |
| 5    | Ngân sách          |
| 6    | UI + hoàn thiện    |

---

## 👨‍🎓 Thông tin sinh viên

* Họ tên: Bùi Duy Khánh
* MSSV: 170124742
* Lớp: DK24TTC7
* Email: khanhbd220801@tvu-onschool.edu.vn

---

## 📌 Hướng phát triển

* Thêm xuất Excel
* Thêm thông báo vượt ngân sách
* Mobile responsive hoàn chỉnh

---

## ⭐ Kết luận

Hệ thống giúp người dùng theo dõi và kiểm soát tài chính hiệu quả thông qua giao diện trực quan và dễ sử dụng.


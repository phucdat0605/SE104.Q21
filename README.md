<!-- Banner -->
<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: none;">
    <img src="https://i.postimg.cc/fyhwXwsK/UIT20-02.png" alt="Trường Đại học Công nghệ Thông tin | University of Information Technology" width="150">
  </a>
</p>

<h1 align="center"><b>ĐỒ ÁN NHẬP MÔN CÔNG NGHỆ PHẦN MỀM (SE104)</b></h1>
<p align="center">
  <img src="https://img.shields.io/badge/Academic_Year-2025--2026-blue?style=flat-square" alt="Năm học">
  <img src="https://img.shields.io/badge/Semester-HK2-orange?style=flat-square" alt="Học kỳ">
  <img src="https://img.shields.io/badge/Language-C%23%20%2F%20Java%20%2F%20JavaScript-brightgreen?style=flat-square" alt="Ngôn ngữ">
</p>

---

##  THÔNG TIN MÔN HỌC
* **Tên môn học:** Nhập môn Công nghệ Phần mềm
* **Nhóm thực hiện:** Nhóm 5
* **Mã lớp:** SE104.Q21
* **Giảng viên hướng dẫn:** Đỗ Thị Thanh Tuyền

---

##  THÀNH VIÊN NHÓM

| STT | MSSV | Họ và Tên | Chức Vụ | Github | Email |
| :---: | :---: | :--- | :---: | :--- | :--- |
| 1 | **23520245** | **Dương Phúc Đạt** | Thành viên | [@phucdat6525](https://github.com/phucdat0605) | 23520245@gm.uit.edu.vn |
| 2 | **23520245** | **Nguyễn Minh Hùng** | Thành viên | [@Art3m1sHun](https://github.com/Art3m1sHun)| 232520568@gm.uit.edu.vn |
| 3 | **23520845** | **Lê Xuân Song Lĩnh**| Thành viên | [@Linh5126](https://github.com/Linh5126)| 23520845@gm.uit.edu.vn |
| 4 | **23520253**|**Ngô Hữu Đạt** | Thành viên |[@Ngo-Dat](https://github.com/Ngo-Dat) | 23520253@gm.uit.edu.vn |
| 5 |**23521311** | **Thái Công Anh Quốc**| Thành viên | [@anhquoc2105](https://github.com/anhquoc2105)| 23521311@gm.uit.edu.vn |

---

# Quản lý thư viện

Ứng dụng quản lý thư viện trên desktop, xây dựng bằng **C# WinForms** và **SQL Server**. Project phục vụ các nghiệp vụ cơ bản của thư viện như quản lý sách, lập thẻ độc giả, mượn sách, trả sách, thu tiền phạt, tra cứu và xem báo cáo.

## Tổng quan

Project được tổ chức theo mô hình 3 lớp:

- `GUI`: giao diện người dùng WinForms.
- `BUS`: xử lý nghiệp vụ và kiểm tra dữ liệu trước khi ghi xuống database.
- `DAL`: truy vấn và cập nhật dữ liệu SQL Server.
- `DTO`: các lớp truyền dữ liệu giữa các tầng.
- `UTILS`: tiện ích dùng chung, hiện có helper kết nối database và quản lý phiên đăng nhập.

Hệ thống có 2 nhóm người dùng chính:

- **Thủ thư**: quản lý dữ liệu và vận hành nghiệp vụ thư viện.
- **Độc giả**: đăng nhập để xem thông tin cá nhân, lịch sử mượn và tra cứu sách.

## Công nghệ sử dụng

- C# .NET Framework 4.7.2
- Windows Forms
- SQL Server
- ADO.NET (`System.Data.SqlClient`)
- Visual Studio

## Chức năng chính

### Thủ thư

- Đăng nhập hệ thống.
- Tiếp nhận sách mới.
- Xóa sách chưa phát sinh lịch sử mượn/trả.
- Lập thẻ độc giả.
- Xóa độc giả chưa phát sinh phiếu mượn hoặc phiếu thu tiền phạt.
- Quản lý thủ thư.
- Cho mượn sách.
- Nhận trả sách, hỗ trợ trả từng cuốn trong cùng một phiếu mượn.
- Thu tiền phạt.
- Tra cứu sách.
- Xem báo cáo thống kê.
- Thay đổi quy định hệ thống.
- Thêm, sửa, xóa thể loại sách.

### Độc giả

- Đăng nhập hệ thống.
- Xem thông tin cá nhân.
- Xem lịch sử mượn sách.
- Tra cứu sách trong thư viện.

## Quy định nghiệp vụ

Các quy định chính được lưu trong bảng `ThamSo`:

- Thời hạn thẻ độc giả theo tháng.
- Tuổi tối thiểu và tối đa khi lập thẻ độc giả.
- Khoảng năm xuất bản hợp lệ khi tiếp nhận sách.
- Số sách được mượn tối đa.
- Số ngày được mượn tối đa.
- Tiền phạt mỗi ngày trả trễ.

Một số quy định được kiểm tra ở cả tầng ứng dụng và SQL Server:

- Độc giả phải còn hạn thẻ mới được mượn sách.
- Độc giả còn nợ tiền phạt không được mượn thêm sách.
- Độc giả không được mượn quá số sách tối đa.
- Sách trả trễ phát sinh tiền phạt.
- Sách tiếp nhận phải nằm trong khoảng năm xuất bản hợp lệ.
- Sách hoặc độc giả đã phát sinh lịch sử mượn/trả không bị xóa trực tiếp để bảo toàn dữ liệu lịch sử.

## Quy định chung và thể loại

Form **Thay đổi quy định** chia làm 2 phần:

- 6 ô phía trên là quy định chung của hệ thống: thời hạn thẻ, tuổi tối thiểu, tuổi tối đa, khoảng năm xuất bản, số sách mượn tối đa và số ngày mượn tối đa.
- Bảng phía dưới chỉ dùng để quản lý tên thể loại sách.

Khi chọn một dòng thể loại, hệ thống chỉ đưa tên thể loại lên ô `Tên thể loại` để sửa hoặc xóa. Việc chọn thể loại không làm thay đổi 6 tham số quy định chung phía trên.

## Cấu trúc thư mục

```text
quanlythuvien/
|-- Database/
|   |-- 01_QuanLyThuVien.sql
|   `-- 02_Fix_Trigger_MuonSach.sql
|-- SourceCode/
|   `-- QuanLyThuVien/
|       |-- QuanLyThuVien.slnx
|       `-- QuanLyThuVien/
|           |-- BUS/
|           |-- DAL/
|           |-- DTO/
|           |-- GUI/
|           |-- UTILS/
|           |-- App.config
|           `-- QuanLyThuVien.csproj
|-- build-check/
|-- .gitignore
`-- README.md
```

## Cơ sở dữ liệu

Database mặc định:

```text
QuanLyThuVien
```

Script chính:

```text
Database/01_QuanLyThuVien.sql
```

Script này tạo database, bảng, khóa, ràng buộc, trigger và dữ liệu mẫu ban đầu.

Chuỗi kết nối nằm trong:

```text
SourceCode/QuanLyThuVien/QuanLyThuVien/App.config
```

Giá trị mặc định:

```xml
<add name="QuanLyThuVienConnection"
     connectionString="Data Source=.;Initial Catalog=QuanLyThuVien;Integrated Security=True"
     providerName="System.Data.SqlClient" />
```

Nếu máy dùng SQL Server instance khác, sửa lại `Data Source`. Ví dụ:

```text
Data Source=.\SQLEXPRESS
```

## Cách chạy project

1. Mở SQL Server Management Studio.
2. Chạy file `Database/01_QuanLyThuVien.sql`.
3. Mở project bằng Visual Studio:

```text
SourceCode/QuanLyThuVien/QuanLyThuVien.slnx
```

Hoặc mở trực tiếp file:

```text
SourceCode/QuanLyThuVien/QuanLyThuVien/QuanLyThuVien.csproj
```

4. Kiểm tra chuỗi kết nối trong `App.config`.
5. Build và chạy ứng dụng.

Màn hình đầu tiên là form đăng nhập.

## Tài khoản mẫu

### Thủ thư

```text
Tên đăng nhập: thuthu01
Mật khẩu: admin123
```

```text
Tên đăng nhập: thuthu02
Mật khẩu: admin123
```

### Độc giả

```text
Tên đăng nhập: docgia01
Mật khẩu: 123456
```

```text
Tên đăng nhập: docgia02
Mật khẩu: 123456
```

Các tài khoản độc giả demo khác:

```text
docgia03 / 123456
docgia04 / 123456
docgia05 / 123456
docgia06 / 123456
docgia07 / 123456
docgia08 / 123456
docgia09 / 123456
```

## Ghi chú khi sử dụng

- Nếu đang mở file `.exe`, Visual Studio có thể không build đè được do file đang bị khóa. Hãy đóng ứng dụng rồi build lại.
- Xóa sách chỉ áp dụng cho sách chưa phát sinh phiếu mượn/trả.
- Xóa độc giả chỉ áp dụng cho độc giả chưa phát sinh phiếu mượn hoặc phiếu thu tiền phạt.
- Dữ liệu đã phát sinh lịch sử được giữ lại để phục vụ tra cứu, báo cáo và bảo toàn liên kết dữ liệu.
- Project phù hợp cho mục đích học tập, demo và đồ án môn học.


##  HÌNH ẢNH MINH HỌA

<img width="542" height="408" alt="image" src="https://github.com/user-attachments/assets/07e20c9f-22ac-4d3c-87d4-5502e19b01bf" />
<img width="1146" height="651" alt="image" src="https://github.com/user-attachments/assets/80a849c7-f023-44db-877a-27d887e07d4f" />
<img width="1145" height="757" alt="image" src="https://github.com/user-attachments/assets/c8f343ad-63e9-4fb8-bc07-77fe71c7e5b0" />




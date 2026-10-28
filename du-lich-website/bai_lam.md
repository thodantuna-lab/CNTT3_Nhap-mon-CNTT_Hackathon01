# BÀI LÀM – HACKATHON 01

- **Mã đề:** 19
- **Họ tên:Trần Minh Quân** 
- **Lớp:CNTT3** 
- **Link repository:https://github.com/thodantuna-lab/CNTT3_Nhap-mon-CNTT_Hackathon01/upload** 
- **Hệ điều hành Windows** 

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> pwd
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> ls -Force
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> mv .\lich_trinh.txt .\docs\
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> mv .\logo_du_lich.PNG .\media\
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> cp .\media\logo_du_lich.PNG .\backup\
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> rm .\temp_274.tmp
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> cd .\logs\
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website\logs> ls
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website\logs> cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

    Directory:
    C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026  10:46 AM                docs
d-----        10/28/2026  10:46 AM                media
d-----        10/28/2026  10:46 AM                data
d-----        10/28/2026  10:46 AM                logs
d-----        10/28/2026  10:46 AM                backup

Path
----
C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website
 Directory:
    C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026  10:46 AM                backup
d-----        10/28/2026  10:48 AM                data
d-----        10/28/2026  10:46 AM                docs
d-----        10/28/2026  10:48 AM                logs
d-----        10/28/2026  10:46 AM                media
------        10/27/2026   1:32 AM             66 .env
-a----        10/27/2026   1:32 AM             58 lich_trinh.txt
-a----        10/27/2026   1:32 AM           4471 logo_du_lich.PNG
------        10/27/2026   1:32 AM             22 temp_274.tmp
Directory:
    C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           1044 travel.log
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> gc .\logs\travel.log |Select-String "ERROR" > .\logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-08-28 08:30:34 [ERROR] Khong tim thay trang /tour-he (404)
2026-08-28 08:36:34 [ERROR] Giu cho that bai

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> .\auto_report.ps1

```

### Kết quả hiển thị

```text



===BAO CAO LOI===

2026-08-28 08:30:34 [ERROR] Khong tim thay trang /tour-he (404)
2026-08-28 08:36:34 [ERROR] Giu cho that bai
2026-08-28 08:42:34 [ERROR] Het thoi gian cho (timeout)
2026-08-28 08:51:34 [ERROR] Giu cho that bai
2026-08-28 08:54:34 [ERROR] Khong tim thay trang /tour-he (404)
2026-08-28 09:09:34 [ERROR] Khong tim thay trang /tour-he (404)

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> (gc .\logs\travel.log | Select-String "ERROR").count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> "===TONG HOP LOG===" > .\logs\tong_hop.txt
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> gc .\logs\travel.log |Select-String "WARNING" >> .\logs\tong_hop.txt
PS C:\Users\admin\Downloads\starter-kit\starter-kit\du-lich-website> (gc .\logs\travel.log |Select-String "ERROR").count >> .\logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
===TONG HOP LOG===

2026-08-28 08:33:34 [WARNING] Thoi gian tai trang cham
2026-08-28 08:45:34 [WARNING] Thoi gian tai trang cham
2026-08-28 09:15:34 [WARNING] Thoi gian tai trang cham


6

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/dat_tour_thang_8.xlsx`, không cần ghi vào đây.

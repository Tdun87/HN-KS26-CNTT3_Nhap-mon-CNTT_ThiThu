# bai_lam

# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên: Nguyễn Tiến Dũng**
- **Lớp: HN-KS26-CNTT 3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS): Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```bash
pwd
Get-ChildItem -Recurse -Force
mv .\Nhap_Hang.txt .\docs\
mv .\Logo_Van_Phong_Pham.PNG media
cp .\media\ .\backup\
rm .\temp_131.tmp
cd .\logs\
ls
cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```
    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   9:14 AM                backup
d-----        10/23/2026   9:10 AM                data
d-----        10/23/2026   9:13 AM                docs
d-----        10/23/2026   9:09 AM                logs
d-----        10/23/2026   9:13 AM                media
-a----        10/19/2026   9:41 AM             78 .env
-a----        10/19/2026  10:00 AM           2253 bai_lam.md

    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website\backup

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   9:14 AM                media

    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website\data

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6105 Don_Ban_Thang_10.xlsx

    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website\docs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM             51 Nhap_Hang.txt

    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website\logs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           1053 Shop.log

    Directory: C:\Users\Admin\OneDrive\Đính kèm\starter-kit\starter-kit\van-phong-pham-website\media

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 Logo_Van_Phong_Pham.PNG
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```bash
Get-Content .\logs\Shop.log | Select-String "ERROR" > .\logs\daily_report.txt
Get-Content .\logs\Shop.log | Select-String "ERROR" | Select-Object -First 2
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.
> 
- [x]  Heading 1: tên dự án
- [x]  Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x]  Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x]  Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x]  Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x]  Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```bash
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process
.\auto_report.ps1
```

### Nội dung file logs/auto_report.txt

```

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```bash
(Get-Content .\logs\Shop.log | Select-String "ERROR").Count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```
6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```bash
"=== TONG HOP LOG ===" > .\logs\tong_hop.txt
Get-Content .\logs\Shop.log | Select-String "WARNING" >> .\logs\tong_hop.txt
Get-Content .\logs\Shop.log | Select-String "ERROR" >> .\logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```
=== TONG HOP LOG ===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
>
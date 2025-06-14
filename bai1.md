# Mẫu Thực hành
Bài đầu : Tìm hiểu NGINX trong local
```
NGINX/
├── index.html 👈 Trang web tĩnh (FE)
├── mime.types 📄 Các định dạng MIME
├── nginx.conf ⚙️ Cấu hình chính
├── nginx.exe 🚀 File chạy Nginx
├── logs/ 📁 Log truy cập & lỗi
│ ├── access.log
│ ├── error.log
│ └── nginx.pid
└── temp/
```
# 📁 Giải Thích Cấu Trúc Thư Mục NGINX

Dưới đây là các thành phần phổ biến trong thư mục Nginx và ý nghĩa của chúng:

## 📄 `index.html`
Trang web tĩnh (Frontend) – đây là file được Nginx hiển thị mặc định khi người dùng truy cập vào `http://localhost`.

---

## 📄 `mime.types`
Chứa danh sách các kiểu MIME – giúp Nginx biết cách gán đúng `Content-Type` cho các file như `.html`, `.css`, `.js`, `.png`, v.v.

---

## ⚙️ `nginx.conf`
File cấu hình chính của Nginx – định nghĩa:
- Port lắng nghe (`listen`)
- Thư mục chứa tài nguyên (`root`)
- Trang mặc định (`index.html`)
- Các rule như `location`, `proxy_pass`, `cache`,...

---

## 🚀 `nginx.exe`
File thực thi chính – khi bạn chạy file này, Nginx sẽ đọc file `nginx.conf` và khởi chạy server trên Windows.

Lệnh chạy:
```bash
.\nginx.exe -c nginx.conf
```
## 📁 logs/
Thư mục ghi lại các hoạt động và lỗi khi Nginx hoạt động.

- 📄 **access.log**  
  Ghi lại mọi request từ người dùng: IP, thời gian, URL, mã trạng thái,...

- 📄 **error.log**  
  Ghi lại lỗi hệ thống: file không tồn tại, sai cấu hình, lỗi kết nối backend,...

- 🧠 **nginx.pid**  
  Ghi lại ID của tiến trình Nginx đang chạy – dùng để `stop`, `reload`, hoặc `ngắt` tiến trình Nginx đúng cách.

---

## 📁 temp/
Thư mục tạm – dùng để:

- Tạm lưu **cache**
- Lưu file khi **upload**
- Chứa session hoặc buffer khi **kết nối backend** nếu có cấu hình sử dụng

---

## ✅ Bảng Tóm Tắt

| Thành phần      | Mô tả ngắn                                       |
|------------------|--------------------------------------------------|
| `index.html`     | Giao diện frontend (trang web tĩnh)             |
| `mime.types`     | Kiểu MIME để trình duyệt hiểu file              |
| `nginx.conf`     | Cấu hình chính của Nginx                        |
| `nginx.exe`      | File chạy chính khởi động Nginx trên Windows    |
| `logs/`          | Ghi lại lịch sử truy cập và lỗi hệ thống        |
| `temp/`          | Tạm lưu cache, upload, buffer backend nếu cần   |

---

> 📌 **Lưu ý:** Những thư mục và file này thường nằm cùng thư mục với `nginx.exe`. Bạn có thể gói gọn chúng trong 1 folder để chia sẻ hoặc backup nhanh chóng.
## 📁 Mục Lục

- [Tổng quan về cấu trúc Nginx](./Nginx/tong-quan.md)
- [Giải thích logs/ và nginx.pid](./Nginx/logs.md)
- [Thư mục tạm temp/ dùng làm gì?](./Nginx/temp.md)
- [File mime.types là gì?](./Nginx/mime.md)
- [Cấu hình nginx.conf cơ bản](./Nginx/nginx-conf.md)
- [Cách chạy nginx.exe trên Windows](./Nginx/chay-nginx.md)

> 🧭 Xem chi tiết trong thư mục [`/Nginx`](./NGINX)

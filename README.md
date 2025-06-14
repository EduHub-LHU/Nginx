# 🚀 Nginx Là Gì? Dùng Để Làm Gì? Cách Setup Nginx Trên Windows 🧠

## ✅ Nginx Là Gì?

**Nginx** (đọc là "engine-x") là một **web server** mã nguồn mở cực kỳ mạnh mẽ và phổ biến.

Nó thường được dùng để:
- Làm **Web Server**
- Làm **Reverse Proxy** (chuyển tiếp request đến server khác)
- Làm **Load Balancer** (phân phối tải đến nhiều server)
- Làm **Cache Server** (giảm tải và tăng tốc)

---

## 🔧 Nginx Dùng Để Làm Gì?

| Chức năng          | Mô tả đơn giản                                                   |
|---------------------|------------------------------------------------------------------|
| 🌍 Web Server       | Host trang web tĩnh hoặc động                                    |
| 🔁 Reverse Proxy     | Chuyển request từ port ngoài (80/443) vào app nội bộ (5000, 3000...)|
| ⚖️ Load Balancer     | Phân tải đến nhiều server backend                               |
| 🧠 Cache             | Lưu kết quả request để tăng tốc truy cập                        |
| 🔐 SSL Gateway       | Thiết lập HTTPS (SSL) dễ dàng                                    |

---

## 💻 Cách Setup Nginx Trên Windows

### Bước 1: Tải Nginx

- Truy cập trang chính thức: [https://nginx.org/en/download.html](https://nginx.org/en/download.html)
- Tải bản **nginx/Windows (zip)** mới nhất

### Bước 2: Giải nén và chạy

```bash
# Ví dụ: C:\nginx\
cd C:\nginx
start nginx
```
## ✅ Bước 3: Truy Cập Thử

Mở trình duyệt và truy cập địa chỉ: 


Nếu thấy dòng **“Welcome to nginx!”** thì bạn đã setup thành công 🎉

---

## 🧠 Các Khái Niệm Cơ Bản Cần Biết Về Nginx

| **Khái niệm**              | **Ý nghĩa**                                                                 |
|----------------------------|------------------------------------------------------------------------------|
| `server block`            | Giống như Virtual Host – dùng để tách các site khác nhau                    |
| `location block`          | Xử lý route cụ thể (ví dụ: `/api/`, `/images/`,...)                         |
| `reverse proxy`           | Nginx đứng giữa người dùng và backend như NodeJS, Flask, ASP.NET,...        |
| `upstream`                | Nhóm các backend server để thực hiện load balancing                         |
| `cache control`           | Cách Nginx lưu trữ tạm nội dung để tăng tốc tải trang                       |
| `access log / error log`  | Ghi lại nhật ký truy cập và lỗi hệ thống server                             |

---

## 📝 Ví Dụ `nginx.conf` Đơn Giản

```nginx
http {
    server {
        listen 80;
        server_name localhost;

        location / {
            root html;
            index index.html;
        }

        location /api/ {
            proxy_pass http://localhost:5000/;
        }
    }
}
## 🔍 Giải Thích

- Truy cập `http://localhost` sẽ load file `index.html` trong thư mục `html` (mặc định của Nginx).
- Truy cập `http://localhost/api/` sẽ được **proxy** đến server backend đang chạy ở `localhost:5000`.

---

## 🎯 Kết Luận

- **Nginx** là một Web Server nhẹ, nhanh, mã nguồn mở và hoàn toàn miễn phí.
- Hoạt động tốt trên **Windows, macOS và Linux**.
- Rất hữu ích trong các trường hợp:

  - ✅ Deploy ứng dụng **WebGL**
  - ✅ Tự chạy các **API backend** như NodeJS, Flask, Fastify,...
  - ✅ Tự cấu hình domain tùy chỉnh, SSL/HTTPS và reverse proxy

---

## 📌 Tài Nguyên Tham Khảo

- 🌐 Trang chủ: [https://nginx.org](https://nginx.org)
- 📘 Tài liệu chính thức: [https://nginx.org/en/docs/](https://nginx.org/en/docs/)
- 🔍 So sánh Nginx và Apache: [https://kinsta.com/blog/nginx-vs-apache/](https://kinsta.com/blog/nginx-vs-apache/)

---
```
[Bài tiếp theo](bai1.md)

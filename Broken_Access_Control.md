
# 🛡️ Broken Access Control

---

## Cài đặt môi trường Docker

Đầu tiên hãy tải các challenge về bằng cách `git clone`:

```bash
git clone https://github.com/Forgebreaker/OWASP_Top_10_2021.git
```

Chạy Docker (Lưu ý: chỏ đến địa chỉ có file `.yaml` để chạy docker):
![BAC](images/Picture1.png)
```bash
docker compose up -d
```

Sau khi chạy docker, ta sẽ vào bài lab tại địa chỉ:

```
http://127.0.0.1:1001
```
![BAC](images/Picture2.png)
---

## Phân tích

- Vào **View Page Source** để xem có thể khai thác được thông tin gì không?
![BAC](images/Picture3.png)
- Thu thập được tài khoản và mật khẩu:

```
guest / guest
```
![BAC](images/Picture4.png)
→ Dùng để đăng nhập vào hệ thống.

---

## Phân tích code

- Sau khi đăng nhập ở trang `index.php`, dữ liệu được lấy từ file `database.sql` và kiểm tra tại bảng `users`, truy vấn theo cột `account_number`.
- Nếu đăng nhập thành công sẽ chuyển đến trang:

```
account.php?account_number=
```
![BAC](images/Picture5.png)
![BAC](images/Picture6.png)
---

## Kiểm tra file database.sql
![BAC](images/Picture7.png)
Truy cập trực tiếp vào:

```
http://127.0.0.1:1001/account.php?account_number=8073
```
<<<<<<< HEAD
![BAC](images/Picture8.png)
=======
![BAC](images/Picture8.png)
>>>>>>> 43ea050 (Thêm hình ảnh minh họa)

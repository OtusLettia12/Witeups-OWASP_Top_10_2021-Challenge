
# 🧱 Insecure Design

---

## Cài đặt môi trường

*Note: vẫn như cài đặt ở phần 01*

```
http://127.0.0.1:4004/
```

---

## Phân tích

- Có giao diện login với tùy chọn "create a new otp"
- Truy cập: `http://127.0.0.1:4004/generator.php`
- Các file chính: `index.php`, `generator.php`, `0f1dc3a4a495befc4fd568aa151b6c8b.db`
- Kết nối Redis, đăng nhập yêu cầu ID: `CVE-170144` và OTP

---

## Vấn đề

- DB SQLite chỉ cho đọc: `attempt to write a readonly database`
- Redis giới hạn số lần thử tạo OTP
- Cần sử dụng bypass bằng thay đổi IP giả (spoofed IP)

---

## Python Bypass Code

```python
# Code bypass Redis và tạo OTP liên tục (xem nội dung đầy đủ trong writeup gốc)
...
device_id = "CVE-170144"
bypass_ctf(device_id)
```

---

## Flag

```
Device ID: CVE-170144
OTP: 01234
```

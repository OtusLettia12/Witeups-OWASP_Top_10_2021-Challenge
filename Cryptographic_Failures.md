
# 🔐 Cryptographic Failures

---

## Cài đặt môi trường

*Note: vẫn như cài đặt ở phần 01*

```
http://127.0.0.1:2002/
```

---

## Phân tích

- Vẫn đăng nhập được bằng tài khoản mặc định: `guest/guest`
- Khi thử truy cập: `http://127.0.0.1:2002/account.php?account_number=8073` thì bị chuyển hướng về: `http://127.0.0.1:2002/account.php?account_number=1002`

---

## Phân tích code

![CF](images/Picture9.png)

- `index.php`: mật khẩu được mã hóa bằng **MD5**

![CF](images/Picture10.png)
- `account.html`: nếu đăng nhập bằng ID `8073` thì có FLAG, nếu không sẽ trả về `"Is that all you can do? Try something better!"`

![CF](images/Picture11.png)
- `database.sql`: xác nhận tất cả mật khẩu được mã hóa bằng MD5

---

## Giải pháp

- Dùng tool online để giải mã MD5: https://10015.io/tools/md5-encrypt-decrypt

![CF](images/Picture12.png)
- Đăng nhập với:

```
Username: bountyboys
Password: power
```
![CF](images/Picture13.png)
---

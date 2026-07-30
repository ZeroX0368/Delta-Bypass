# PlatoRelay Bypass

Tự động bypass checkpoint link của PlatoRelay và trả về key.

---

## Yêu cầu

- Python **3.11** trở lên

---

## Cài đặt thư viện

```bash
pip install -r requirements.txt
```

Hoặc cài thủ công từng gói:

```bash
pip install pycryptodome cryptography crypto curl-cffi numpy Pillow requests
```

---

## Sử dụng

### Chạy trực tiếp

```bash
python main.py
```

Nhập URL PlatoRelay khi được hỏi:

```
URL: https://auth.platorelay.com/a?d=XXXXXXXX
```

### Dùng như thư viện

```python
from main import getKey, get_token

# Bypass link và lấy key
key = getKey("https://auth.platorelay.com/a?d=XXXXXXXX", verbose_cb=print)
print(key)

# Chỉ giải captcha và lấy token
token = get_token()
print(token)
```

---

## Danh sách thư viện (`requirements.txt`)

| Package | Phiên bản | Mô tả |
|---|---|---|
| `pycryptodome` | ≥ 3.23.0 | Mã hóa AES-CTR (`Crypto`) |
| `cryptography` | ≥ 49.0.0 | Thư viện mã hóa cấp cao |
| `crypto` | ≥ 1.4.1 | Tiện ích crypto bổ sung |
| `curl-cffi` | ≥ 0.15.0 | HTTP client giả lập Chrome |
| `numpy` | ≥ 2.4.6 | Xử lý mảng và tính toán số học |
| `Pillow` | ≥ 12.3.0 | Giải mã GIF captcha (`PIL`) |
| `requests` | ≥ 2.34.2 | HTTP requests |

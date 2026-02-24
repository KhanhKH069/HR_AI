# Evaluation for Paragen
## 1. Thành viên
- Vũ Nam Khánh
- Nguyễn Văn Lâm Hùng
---

## 2. Hướng dẫn đồng bộ môi trường ảo, thư viện

Dự án sử dụng **uv** để quản lý môi trường với tốc độ cao và độ ổn định tuyệt đối.

### 2.1. Cài đặt uv

Nếu máy bạn chưa có `uv`, hãy cài đặt theo hướng dẫn tại: [uv installation](https://docs.astral.sh/uv/getting-started/installation/).

### 2.2. Đồng bộ môi trường (Một lệnh duy nhất)

Tại thư mục gốc của dự án `eval_paragen`, chạy lệnh sau để tự động tạo môi trường ảo và cài đặt tất cả thư viện:

```bash
uv sync
```

### 2.3. Sử dụng môi trường ảo

* **Để chạy script:** Sử dụng `uv run python script_cua_ban.py`
* **Để mở Jupyter Notebook:** Bạn chỉ cần chọn kernel là môi trường ảo nằm trong thư mục `.venv` mà `uv` vừa tạo ra.


## 3. Hướng dẫn làm việc chung (Git & Code Style)

Để đảm bảo code luôn sạch và tránh xung đột, toàn bộ thành viên cần tuân thủ quy trình sau:

### 3.1. Cài đặt công cụ hỗ trợ

* **Ruff Extension:** Cài đặt trên VSCode để tự động sửa lỗi và định dạng code khi nhấn `Ctrl + S`.
* **Kích hoạt Kiểm tra Tự động (Pre-commit):** Đây là bước **bắt buộc** sau khi cài đặt môi trường để đảm bảo code của bạn đạt chuẩn trước khi đẩy lên GitHub.
```bash
uv run pre-commit install
```



### 3.2. Quy trình đẩy code (Git Workflow)

1. **Tải Repo về máy (nếu chưa có):**
```bash
git clone https://github.com/KhanhKH069/HR_AI.git
cd HR_AI

```


2. **Tạo nhánh mới trước khi làm việc:**
> Tránh làm việc trực tiếp trên nhánh `main`.


```bash
# Thay 'ten-cua-ban' bằng tên viết liền không dấu, ví dụ: 'hung-ai'
git checkout -b feature/ten-cua-ban
```


3. **Lưu và Đẩy code:**
```bash
git status                         # Kiểm tra các file đã thay đổi
git add .                          # Thêm tất cả thay đổi vào hàng chờ
git commit -m "Mô tả ngắn gọn việc bạn đã làm"
```


> **Lưu ý:** Nếu lệnh `commit` báo lỗi, đó là do **Pre-commit** đang sửa lại định dạng cho bạn. Hãy `git add .` lại lần nữa và `commit` lại là xong.


```bash
# Đẩy nhánh cá nhân lên repo lần đầu tiên
git push -u origin feature/ten-cua-ban
```


4. **Cập nhật code mới nhất từ nhóm:**
```bash
git checkout main
git pull origin main
git checkout feature/ten-cua-ban
git merge main
```



---

### Mẹo nhỏ:

* Nếu bạn muốn kiểm tra toàn bộ lỗi của dự án mà không cần commit, hãy chạy: `uv run ruff check .`
* Để tự động định dạng lại toàn bộ file: `uv run ruff format .`

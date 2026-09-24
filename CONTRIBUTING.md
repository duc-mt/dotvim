# Contributing to dotvim

Chào mừng bạn đã quan tâm đóng góp vào dự án! Để đảm bảo chất lượng, sự ổn định và dễ dàng bảo trì, vui lòng tuân thủ một số nguyên tắc dưới đây.

## 1. Commit Message Guidelines

Dự án này sử dụng [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/). Mỗi commit message nên có dạng:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```
Các `type` được hỗ trợ:
- `feat`: Tính năng mới (ví dụ: thêm plugin mới)
- `fix`: Sửa lỗi
- `docs`: Sửa tài liệu (`README.md`, `docs/MAINTENANCE.md`)
- `style`: Thay đổi không ảnh hưởng đến logic (khoảng trắng, format...)
- `refactor`: Sửa đổi code không phải fix bug cũng không phải thêm tính năng
- `test`: Thêm/sửa script test
- `chore`: Cập nhật CI/CD, script build, pre-commit

## 2. CI/CD & Local Checks

Trước khi tạo Pull Request, hãy đảm bảo bạn đã chạy các bài test ở máy local:
1. **Kiểm tra cú pháp**: Chạy `pre-commit run --all-files` hoặc `bash scripts/run-vint.sh`.
2. **Kiểm tra khởi động**: Chạy `bash scripts/startup-smoke-test.sh`. Bắt buộc phải pass 100%.
3. **Kiểm tra hygiene**: Nếu bạn sửa file trong `ftplugin/`, hãy chạy `bash scripts/check-ftplugin-hygiene.sh`.

Mọi thay đổi không vượt qua CI trên GitHub Actions sẽ không được merge.

## 3. Quản lý Plugin và Kiến trúc

Nếu bạn muốn thêm, sửa, hoặc lazy-load plugin, hãy đọc kỹ [MAINTENANCE.md](docs/MAINTENANCE.md). Tài liệu này chứa những quy tắc sống còn về việc sử dụng Submodules và cơ chế autoload của Vim trong repo này.

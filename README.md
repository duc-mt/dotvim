# 🚀 DotVim (`duc-mt/dotvim`)

![CI Status](https://github.com/duc-mt/dotvim/actions/workflows/validate.yml/badge.svg)
![Security Scan](https://github.com/duc-mt/dotvim/actions/workflows/security-scan.yml/badge.svg)

Một bộ cấu hình Vim chuyên nghiệp, tập trung vào **tốc độ khởi động siêu tốc**, **độ an toàn cao**, và **kiến trúc Lazy-Load thông minh**. Repository này được thiết kế và quản lý theo chuẩn Infrastructure-as-Code (IaC) để đảm bảo không một thay đổi nào làm gãy cấu hình.

## 🛠 Project Philosophy
- **Zero-cost by default**: Các plugin nặng chỉ được nạp (loaded) khi người dùng mở đúng file type yêu cầu hoặc gọi explicit command (Lazy-Load via `pack/*/opt/`).
- **Hygiene Codebase**: Đóng gói các tính năng vào thư mục `ftplugin/` để ngăn ngừa rò rỉ setting (leaking buffers).
- **Strict CI/CD Gate**: Mọi thay đổi về cấu hình đều phải pass qua lớp kiểm duyệt gắt gao (Lint, Smoke Test, Regression Check).

## 🚀 Installation

Để cài đặt bộ cấu hình này, hãy dùng cờ `--recursive` để clone tất cả các Submodules (Plugins) bên trong.

```bash
git clone --recursive https://github.com/duc-mt/dotvim.git "${HOME}/.vim"
```

## 📂 Architecture (Cấu trúc thư mục)

```text
.vim/
├── vimrc                       # Main entry point (được gọi đầu tiên)
├── pack/                       # Chứa tất cả Vim Plugins (quản lý bằng git submodules)
│   ├── plugins.vim             # File config cài đặt cho các plugin
│   ├── */start/                # Eager-loaded plugins (chạy ngay lúc mở Vim)
│   └── */opt/                  # Lazy-loaded plugins (chỉ nạp khi cần qua lệnh `packadd`)
├── ftplugin/                   # File-type cụ thể, chỉ được chạy một lần mỗi buffer
├── ftdetect/                   # Bổ sung các format file mới ngoài mặc định của Vim
├── template/                   # Boilerplate/Snippet tiêm vào file mới tự động
├── wordlist/                   # Chứa dictionary, abbreviation, autocorrect
├── docs/                       # Tài liệu thiết kế và kiến trúc
│   └── MAINTENANCE.md          # 🚨 ĐỌC KỸ file này nếu muốn sửa code/thêm plugin
├── scripts/                    # Chứa Shell scripts dùng cho Test và CI/CD
└── .github/                    # CI/CD Workflows và Issue/PR Templates
```

## 🤝 Contributing

Chúng tôi hoan nghênh mọi đóng góp! Vui lòng đọc qua [CONTRIBUTING.md](CONTRIBUTING.md) và [MAINTENANCE.md](docs/MAINTENANCE.md) để hiểu rõ rule khi tạo PR.
Tất cả commit trong repo cần được format chuẩn theo **Conventional Commits**.

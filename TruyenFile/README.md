# Hệ Thống Truyền File University 

Đây là một hệ thống demo cho phép giảng viên tải lên các tệp tài liệu, có tùy chọn mã hóa và ký số. Sinh viên có thể xem, tải xuống các tệp này và xác thực chữ ký số. Hệ thống sử dụng WebSocket để giao tiếp giữa client (trình duyệt) và server (Python).

## Tính năng chính

* Tải tệp lên: Giảng viên có thể tải lên các tệp tài liệu.
* Mã hóa tệp: Sử dụng AES-256 để mã hóa nội dung tệp trên client trước khi gửi lên server.
* Ký số tệp: Sử dụng RSA/SHA-256 để ký số tệp, đảm bảo tính toàn vẹn và xác thực nguồn gốc.
* Quản lý lớp học: Giảng viên có thể thêm và xem danh sách các lớp học.
* Lịch sử gửi: Giảng viên có thể xem lại các tệp đã tải lên.
* Quản lý khóa (Giảng viên): Giảng viên có thể tạo và xem cặp khóa RSA (công khai/riêng tư). Khóa riêng tư được sử dụng để ký số.
* Xem và Tải xuống tài liệu (Sinh viên): Sinh viên có thể xem danh sách các tệp được tải lên và tải chúng xuống.
* Giải mã tệp (Sinh viên): Tệp mã hóa sẽ tự động được giải mã khi tải xuống (với khóa AES được server cung cấp cho mục đích demo).
* Xác thực chữ ký (Sinh viên): Sinh viên có thể xác thực chữ ký số của tệp bằng cách sử dụng khóa công khai của giảng viên.
* Quản lý khóa cá nhân (Sinh viên): Sinh viên có thể tạo cặp khóa RSA cá nhân cho mục đích sử dụng sau này (ví dụ: ký nộp bài tập).



## Cấu trúc dự án

Truyen File University/
├── server.py             # Mã nguồn máy chủ Python WebSocket
├── client/
│   └── index.html        # Giao diện người dùng (HTML/CSS/JavaScript)
├── files/                # Thư mục lưu trữ các tệp đã tải lên
├── keys/                 # Thư mục lưu trữ khóa RSA của giảng viên
├── .vscode/
│   ├── launch.json       # Cấu hình khởi chạy và gỡ lỗi VS Code
│   └── settings.json     # Cài đặt workspace VS Code
├── README.md             # Tài liệu dự án
└── requirements.txt      # Danh sách các thư viện Python cần cài đặt


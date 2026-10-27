# Portfolio cá nhân - Phạm Văn Hiệp

Website portfolio/CV cá nhân giới thiệu Phạm Văn Hiệp, các kỹ năng Frontend, một số dự án tiêu biểu và thông tin liên hệ. Giao diện được xây dựng dưới dạng trang web tĩnh, có thể mở trực tiếp bằng trình duyệt hoặc phục vụ qua một web server đơn giản.

## Chức năng

- Giới thiệu cá nhân và định hướng Frontend Developer.
- Trình bày các kỹ năng: HTML5, CSS3, Flexbox, Grid, JavaScript, responsive design, Git/GitHub và Figma.
- Hiển thị các dự án mẫu kèm hình ảnh, mô tả và công nghệ.
- Điều hướng đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Cung cấp khu vực liên hệ và biểu mẫu giao diện.
- Hỗ trợ bố cục responsive trên các kích thước màn hình khác nhau.

> Biểu mẫu liên hệ hiện chỉ là giao diện HTML; dự án chưa có backend để gửi hoặc lưu nội dung biểu mẫu.

## Công nghệ

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện, bố cục và responsive.
- Docker/Nginx (tùy chọn): phục vụ trang tĩnh trong container.

JavaScript được liệt kê trong phần kỹ năng trên trang, nhưng hiện không có tệp JavaScript trong dự án.

## Cấu trúc dự án

```text
lesson05/
├── index.html
├── README.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        ├── avatar.jpg
        ├── bopbop.jpg
        ├── image.png
        ├── thenguyen1.jpg
        └── trần-bình.jpg
```

## Yêu cầu môi trường

### Chạy trực tiếp

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Không cần cài Node.js, không cần cài thư viện và không cần biên dịch.
- Để chạy qua web server cục bộ, cài Python 3 hoặc dùng tiện ích Live Server của Visual Studio Code.

### Chạy bằng Docker

- Docker Desktop trên Windows/macOS, hoặc Docker Engine trên Linux.
- Không cần Dockerfile; có thể dùng trực tiếp image `nginx:alpine` để phục vụ các tệp tĩnh.

## Cài đặt và chạy thử

Tải hoặc sao chép toàn bộ dự án về máy, sau đó mở terminal tại thư mục chứa `index.html`. Phải giữ nguyên thư mục `assets` bên cạnh `index.html` để CSS và hình ảnh được tải đúng.

### Windows

Mở PowerShell tại thư mục dự án. Có thể mở trang trực tiếp:

```powershell
Start-Process .\index.html
```

Hoặc chạy web server cục bộ bằng Python 3:

```powershell
py -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng server bằng `Ctrl+C`.

### macOS

Mở Terminal, chuyển đến thư mục dự án (thay đường dẫn ví dụ bên dưới bằng vị trí thực tế):

```bash
cd "/duong-dan/toi/lesson05"
```

Mở trực tiếp trong Safari:

```bash
open index.html
```

Hoặc chạy server bằng Python 3:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng server bằng `Ctrl+C`.

### Linux

Mở terminal, chuyển đến thư mục dự án (thay đường dẫn ví dụ bên dưới bằng vị trí thực tế):

```bash
cd "/duong-dan/toi/lesson05"
```

Mở trực tiếp bằng trình duyệt mặc định:

```bash
xdg-open index.html
```

Hoặc chạy server bằng Python 3:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng server bằng `Ctrl+C`.

### Docker

Đảm bảo Docker đang chạy và terminal hiện tại đang ở thư mục dự án. Lệnh sau gắn thư mục dự án ở chế độ chỉ đọc vào Nginx và mở trang tại cổng `8080`.

**Windows PowerShell:**

```powershell
docker run --rm -d --name lesson05-portfolio -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS/Linux:**

```bash
docker run --rm -d --name lesson05-portfolio -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Mở <http://localhost:8080> để kiểm tra. Dừng container bằng:

```bash
docker stop lesson05-portfolio
```

Nếu cổng `8080` đã được sử dụng, đổi phần `-p 8080:80` thành một cổng trống khác, chẳng hạn `-p 8081:80`, rồi truy cập cổng tương ứng.

## Cấu hình và tùy chỉnh

Dự án hiện không sử dụng tệp cấu hình riêng, biến môi trường, dịch vụ API hoặc bước build.

- Chỉnh nội dung, tiêu đề trang và thông tin hiển thị trong `index.html`.
- Chỉnh màu sắc, bố cục và breakpoint responsive trong `assets/css/styles.css`.
- Thay ảnh trong `assets/img/`; nếu đổi tên hoặc vị trí ảnh, cập nhật đường dẫn `src` tương ứng trong `index.html`.
- Khi chạy Docker, cổng truy cập được cấu hình qua tham số `-p` của lệnh `docker run`.
- Muốn triển khai biểu mẫu liên hệ, cần bổ sung dịch vụ xử lý phía máy chủ hoặc tích hợp một dịch vụ biểu mẫu phù hợp.

## Kiểm tra sau khi chạy

1. Mở trang bằng một trong các cách ở trên.
2. Kiểm tra các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ qua thanh điều hướng.
3. Xác nhận CSS và ảnh được tải; nếu thiếu, kiểm tra tên tệp, đường dẫn và chữ hoa/thường.
4. Thay đổi kích thước cửa sổ hoặc mở trên thiết bị di động để kiểm tra bố cục responsive.
5. Khi dùng Docker, xác nhận container đang chạy bằng `docker ps` và truy cập đúng cổng đã ánh xạ.

## Thông tin liên hệ

- Tên hiển thị: **Phạm Văn Hiệp**
- Email hiển thị trên trang: [qvanhiep08@gmail.com](mailto:qvanhiep08@gmail.com)
- GitHub và LinkedIn: trang hiện có nội dung hiển thị nhưng liên kết đang là placeholder; hãy cập nhật URL thật trong `index.html` trước khi sử dụng.

Phần liên hệ thứ hai trong trang cũng chứa các dữ liệu mẫu như địa chỉ Chicago, số điện thoại và email `mail@mail.com`. Vui lòng thay bằng thông tin thật hoặc xóa trước khi công khai website.
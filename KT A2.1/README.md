# Portfolio cá nhân — Phạm Dương Huy

Trang portfolio/CV cá nhân giới thiệu Phạm Dương Huy, kỹ năng, một số dự án tiêu biểu và thông tin liên hệ. Giao diện được xây dựng bằng HTML và CSS thuần, có bố cục responsive cho máy tính, máy tính bảng và điện thoại.

## Dự án

- **Tên:** Portfolio cá nhân — Phạm Dương Huy
- **Loại:** Website tĩnh (frontend)
- **Tác giả:** Phạm Dương Huy
- **Thư mục ứng dụng:** `KT A2.1`
- **Trang chính:** `KT A2.1/index.html`

## Mô tả

Đây là trang giới thiệu cá nhân theo dạng portfolio/CV. Người xem có thể tìm hiểu phần giới thiệu, các kỹ năng, dự án tiêu biểu và cách liên hệ với tác giả. Nội dung trang được viết bằng tiếng Việt.

## Chức năng

- Điều hướng đến các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Giới thiệu thông tin cá nhân và định hướng phát triển web.
- Trình bày danh sách kỹ năng.
- Hiển thị các thẻ dự án kèm hình ảnh, mô tả và nhãn công nghệ/chủ đề.
- Cung cấp liên kết email và LinkedIn.
- Bố cục tương thích với nhiều kích thước màn hình.

> Một số liên kết “Xem chi tiết” trong thẻ dự án hiện là liên kết mẫu (`#`), chưa dẫn đến trang chi tiết riêng.

## Công nghệ

- **HTML5:** cấu trúc và nội dung trang.
- **CSS3:** giao diện, bố cục responsive, Flexbox và CSS Grid.
- **Ảnh tĩnh:** lưu trong `KT A2.1/assets/img/`.

Dự án không sử dụng framework JavaScript, backend, cơ sở dữ liệu hoặc công cụ build. Các kỹ năng JavaScript, GitHub và Figma được liệt kê trên trang là kỹ năng của tác giả, không phải dependency cần cài để chạy website.

## Cấu trúc thư mục

```text
.
├── README.md
└── KT A2.1/
    ├── index.html
    └── assets/
        ├── css/
        │   └── styles.css
        └── img/
            ├── Huydz.png
            ├── Lớp học.jpg
            ├── lịch sử.jpg
            ├── nông nghiệp.jpg
            └── robot hình người.png
```

## Yêu cầu và môi trường

### Để xem trang

- Trình duyệt hiện đại có hỗ trợ HTML5 và CSS3, ví dụ Chrome, Edge, Firefox hoặc Safari.
- Không cần cài Node.js, npm, cơ sở dữ liệu hay backend.
- Có thể mở `KT A2.1/index.html` trực tiếp trong trình duyệt. Để có trải nghiệm ổn định hơn, hãy chạy một máy chủ HTTP tĩnh như hướng dẫn bên dưới.

### Để chạy bằng Docker

- Đã cài và khởi động Docker Desktop (Windows/macOS), hoặc Docker Engine (Linux).
- Máy có thể tải image `nginx:alpine` trong lần chạy đầu tiên.

## Cài đặt

Dự án không có bước cài dependency. Tải hoặc clone repository, sau đó làm việc trong thư mục `KT A2.1`.

## Cấu hình

- Website hiện không yêu cầu biến môi trường hay tệp cấu hình riêng.
- Không có thông tin bí mật hoặc thông số backend cần khai báo.
- Nếu muốn cập nhật nội dung, chỉnh sửa `KT A2.1/index.html`.
- Nếu muốn thay đổi giao diện, chỉnh sửa `KT A2.1/assets/css/styles.css`.
- Khi thay ảnh, đặt ảnh trong `KT A2.1/assets/img/` và cập nhật đường dẫn tương ứng trong HTML.

## Chạy thử trên Windows

### Mở trực tiếp

Mở File Explorer, đi đến thư mục `KT A2.1` và mở `index.html` bằng trình duyệt.

### Chạy máy chủ HTTP tĩnh (PowerShell)

Mở PowerShell tại thư mục ứng dụng rồi chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có, thử:

```powershell
python -m http.server 8000
```

Truy cập <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

## Chạy thử trên macOS

Mở Terminal, chuyển đến thư mục ứng dụng rồi chạy:

```bash
cd "KT A2.1"
python3 -m http.server 8000
```

Truy cập <http://localhost:8000>. Dừng máy chủ bằng `Control+C`.

## Chạy thử trên Linux

Mở terminal, chuyển đến thư mục ứng dụng rồi chạy:

```bash
cd "KT A2.1"
python3 -m http.server 8000
```

Truy cập <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

> Nếu đang ở thư mục `KT A2.1` thì không cần chạy lại lệnh `cd`. Máy chủ Python chỉ phục vụ tệp tĩnh cho mục đích xem/thử nghiệm.

## Chạy bằng Docker

Docker dùng Nginx để phục vụ trực tiếp các tệp tĩnh trong thư mục `KT A2.1`; không cần tạo image riêng. Hãy chạy các lệnh tại thư mục gốc repository.

### Windows (PowerShell)

```powershell
docker run --rm -d -p 8080:80 --name portfolio-site --mount "type=bind,source=$((Resolve-Path '.\KT A2.1').Path),target=/usr/share/nginx/html,readonly" nginx:alpine
```

### macOS và Linux

```bash
docker run --rm -d -p 8080:80 --name portfolio-site --mount "type=bind,source=$(pwd)/KT A2.1,target=/usr/share/nginx/html,readonly" nginx:alpine
```

Sau khi container khởi động, mở <http://localhost:8080>. Để dừng:

```bash
docker stop portfolio-site
```

Tùy chọn kiểm tra container đang chạy:

```bash
docker ps
```

Nếu cổng `8080` đang được sử dụng, thay `8080:80` bằng một cổng trống khác, chẳng hạn `8081:80`, rồi truy cập cổng tương ứng.

## Kiểm tra

Mở trang theo một trong các cách ở trên, sau đó kiểm tra:

- Trang hiển thị đầy đủ và không thiếu hình ảnh.
- Các liên kết điều hướng đưa đến đúng mục trên trang.
- Bố cục hiển thị phù hợp trên màn hình điện thoại và máy tính.
- Liên kết email mở trình soạn thư; liên kết LinkedIn mở hồ sơ tương ứng.

## Thông tin và liên hệ

- **Tác giả:** Phạm Dương Huy
- **Email:** [phamduonghuyiq@gmail.com](mailto:phamduonghuyiq@gmail.com)
- **LinkedIn:** [linkedin.com/in/phamduonghuy](https://linkedin.com/in/phamduonghuy)

## Bản quyền

Nội dung và hình ảnh trong dự án được sử dụng cho mục đích giới thiệu portfolio cá nhân. Vui lòng liên hệ tác giả trước khi sử dụng lại tài nguyên thuộc quyền sở hữu của tác giả.
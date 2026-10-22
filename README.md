# 5Tech Solution — landing page

Website tĩnh song ngữ, không cần cài dependencies hoặc build. Mã nguồn chạy trực tiếp là thư mục `dist/`.

## Chạy local

Từ thư mục này: `python3 -m http.server 4173 --directory dist`.
Mở `http://localhost:4173/` (VI) và `/en/` (EN).

## Cấu trúc

- `dist/index.html`: nội dung tiếng Việt.
- `dist/en/index.html`: nội dung tiếng Anh.
- `dist/style.css`: nhận diện, layout và responsive tại 760 / 1100px.
- `dist/script.js`: menu mobile, đóng bằng Escape hoặc sau khi chọn liên kết.
- `dist/favicon.svg`, `dist/social-card.png`: nhận diện đề xuất, ảnh chia sẻ.
- `dist/robots.txt`, `dist/sitemap.xml`: cấu hình cho domain đích.

Liên hệ là liên kết email và điện thoại thật được công bố trên Notion. Không có form hoặc hệ thống nhận lead giả. Website không dùng tracker, font từ bên thứ ba hoặc thư viện bên ngoài.

## Rà soát nội dung và thương hiệu

Nguồn đọc ngày 22/10/2026:
- https://5ts.notion.site/5Tech-Solutions-9908f5b4e3b04421b70061412081b632
- https://5ts.notion.site/Get-in-touch-dfdab14a132246a283f0f748e29bf303

Thông tin được nguồn xác nhận: đội ngũ lập trình viên/thiết kế tại Việt Nam; Android/iOS; ưu tiên trải nghiệm; slogan “Innovative ideas, trusted partnership”; email cũ trên Notion là ngvannam5@gmail.com; điện thoại +84.935.357.567. Theo yêu cầu của chủ website, email hiển thị và dữ liệu SEO hiện dùng info@5ts.io.vn. Danh mục dự án hiện giới thiệu Growth Investing và FamilyNestPro theo nội dung công khai từ website sản phẩm. Các lời khẳng định “top”, “uy tín”, khách hàng lớn và kết quả định lượng không được đưa vào.

Flutter, AI/backend: định hướng nội dung theo brief của chủ website, chưa được hồ sơ Notion chính xác nhận bằng dự án cụ thể. Không viết thành chứng nhận hoặc thành tích đã kiểm chứng.

Tên: Notion dùng “5Tech Solutions”, brief dùng “5Tech Solution”. Giao diện dùng logo 5Tech Solutions do chủ website cung cấp; structured data giữ “5Tech Solutions” ở alternateName.

Nhận diện sử dụng logo PNG trong suốt do chủ website cung cấp và bảng màu chính thức: Navy `#012966`, Royal `#0145C2`, Tech `#0162E0`, Bright `#0185F6`, Cyan `#02CFFD`. Giữ slogan nguyên bản, dùng hình sản phẩm tự dựng và tránh ảnh stock công nghệ chung chung.

Địa chỉ chi tiết trên Notion: 523A Do Xuan Hop Street, Phuoc Long Ward, Thu Duc City, Ho Chi Minh, Viet Nam. Theo yêu cầu của chủ website, phần liên hệ và dữ liệu có cấu trúc hiện ghi nhận TP. Hồ Chí Minh và Quảng Ngãi.

## Deploy GitHub Pages với 5ts.io.vn

Workflow `.github/workflows/pages.yml` deploy trực tiếp thư mục `dist/` sau mỗi lần push lên `main`. GitHub Pages được cấu hình với custom domain `5ts.io.vn`.

Tại nhà cung cấp DNS, xóa hai bản ghi A cũ trỏ tới `162.159.143.30` và `172.66.3.26`, sau đó thêm bốn bản ghi A của GitHub Pages:

| Loại | Tên | Giá trị |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `profive.github.io` |

Không thay đổi hoặc xóa các bản ghi MX/TXT email hiện có. Sau khi chuyển hẳn khỏi Sites, có thể xóa hai TXT `_openai-site-verification` và `_cf-custom-hostname` vì GitHub Pages không dùng chúng. Không tạo bản ghi wildcard `*`.

DNS có thể cần đến 24 giờ để cập nhật. Khi GitHub cấp chứng chỉ, bật **Enforce HTTPS** trong **Settings → Pages**, rồi kiểm tra `https://5ts.io.vn`, `/en/`, `robots.txt` và `sitemap.xml`.

Canonical, hreflang, Open Graph và sitemap đã trỏ domain đích `https://5ts.io.vn`. Nếu chọn domain khác, cập nhật toàn bộ URL tuyệt đối trong hai file HTML và sitemap/robots.

## Trước khi công bố rộng rãi

Xác nhận email/điện thoại còn sử dụng, phạm vi dịch vụ Flutter và AI/backend, cùng quyền công bố nội dung dự án trước các chiến dịch quảng bá lớn.

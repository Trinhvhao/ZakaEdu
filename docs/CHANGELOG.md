# Tài liệu sửa đổi website
Nội dung: Sửa đổi trang Index.html

Ngày: 29/12/2024

## 1. Thêm đường dẫn CSS mockup

- Mục tiêu: Thêm file CSS mẫu để cải thiện giao diện và dễ dàng điều chỉnh trong tương lai.

- Thao tác:

Tạo file CSS mockup (nếu chưa có), ví dụ: mockup.css.
Import file CSS vào trong file HTML chính:

 <link href="css/mockup.css" rel="stylesheet" />

Đảm bảo đường dẫn chính xác và kiểm tra file CSS hoạt động đúng cách.

## 2. Sửa phần banner đầu tiên tại trang chủ

- Mục tiêu: Giảm kích thước chữ trên banner đầu tiên để phù hợp hơn với giao diện tổng thể.

- Thao tác:
Mở file cấu hình giao diện (HTML hoặc CSS liên quan).
Tìm phần tử chứa nội dung banner, copy và thay thế
- Điều chỉnh kích thước font trong CSS:
(Đã điều chỉnh trong mockup.css)
- Lưu thay đổi và kiểm tra giao diện.

## 3. Phần 4 giá trị cốt lõi

- Mục tiêu: Giảm bớt nội dung để thông điệp rõ ràng và ngắn gọn hơn.
- Thao tác:
Xác định file chứa phần giá trị cốt lõi (nằm trong trang chủ).
- Tìm phần nội dung, copy và thay thế ở Feature
- Rút gọn nội dung từng giá trị theo định hướng ngắn gọn.
- Lưu thay đổi và kiểm tra lại hiển thị.

## 4. Phần team chuyển thành dạng slideshow

- Mục tiêu: Chuyển hiển thị team từ danh sách cố định sang slideshow để hiện đại và linh hoạt hơn.

- Thao tác:
Xác định phần hiển thị team hiện tại trong mã nguồn.
- Thay thế cấu trúc hiện tại bằng thư viện slideshow (SwiperJS).
- Thêm đường dẫn và thư viên swiper bằng cách kéo thư mục từ project mockup sang project chính (lib/swiper)
```html
 <link href="lib/swiper/swiper-bundle.min.css" rel="stylesheet" />
  <script src="lib/swiper/swiper-bundle.min.js"></script>
```
- Import và cấu hình thư viện slideshow trong JavaScript:
```js
/**
 * Init swiper sliders
 */
function initSwiper() {
  document.querySelectorAll(".init-swiper").forEach(function (swiperElement) {
    let config = JSON.parse(
      swiperElement.querySelector(".swiper-config").innerHTML.trim()
    );

    if (swiperElement.classList.contains("swiper-tab")) {
      initSwiperWithCustomPagination(swiperElement, config);
    } else {
      new Swiper(swiperElement, config);
    }
  });
}

window.addEventListener("load", initSwiper);
```
- Lưu thay đổi và kiểm tra slideshow hoạt động.

## 5. Thêm phần gallery
- Mục tiêu: Hiển thị một gallery ảnh tại trang chủ để thu hút người xem.
- Thao tác: Thêm section mới trong file HTML trang chủ ở project mockup
- Style gallery trong mockup.css
- Thêm các thư viện hỗ trợ:
```js
<script src="lib/imagesloaded/imagesloaded.pkgd.min.js"></script>
 <script src="lib/isotope-layout/isotope.pkgd.min.js"></script>
  <script src="lib/glightbox/js/glightbox.min.js"></script>
  ```
- Lưu thay đổi và kiểm tra hiển thị.

## 6. Sửa phần đối tác thành slide
- Mục tiêu: Dễ nhìn trong màn hình nhỏ
- Thao tác: Copy và thay thế phần đối tác từ prj mockup sang prj chính
- Thêm các thư viện hỗ trợ 

**Ghi chú**
- Sau mỗi thay đổi, kiểm tra kỹ trên các thiết bị khác nhau (PC, tablet, mobile).
- Nếu file Js chưa chỉnh sửa gì nhiều thì có thể copy luôn file js từ prj mockup sang, tương tự với các phần import css và js
- Đảm bảo backup code trước khi thực hiện chỉnh sửa.

Người thực hiện:
**Trinh Van Hao**


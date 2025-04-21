# Plugin Kết nối Zalo OA với WordPress / WooCommerce

## Mô tả
Plugin này giúp kết nối Official Account (OA) Zalo với WooCommerce, tự động gửi tin nhắn thông báo đơn hàng, thay đổi trạng thái, nhắc đánh giá sản phẩm… qua Zalo thay vì email hoặc SMS.

## Tính năng chính

- **Tin giao dịch (transactional message)** gửi cho khách **đã quan tâm OA**  
  - Khi có đơn hàng mới  
  - Khi đơn thay đổi trạng thái  
  - Khi đơn hoàn thành  
  - Nhắc khách đánh giá sản phẩm sau X ngày  

- **Tin ZNS (notification message)** gửi cho khách **chưa quan tâm** và **đã quan tâm OA**  
  - Khi có đơn hàng mới  
  - Khi đơn thay đổi trạng thái  
  - Khi đơn hoàn thành  
  - Lên lịch gửi lại tin lỗi vào 6h sáng hôm sau nếu gửi ZNS phát sinh trong khung giờ 22:00–06:00  
  - Quản lý lịch sử toàn bộ tin đã gửi  
  - Danh sách số điện thoại đã gửi tin  
  - Tự động resend ZNS lỗi vào ngày kế tiếp  

- **Chiến dịch truyền thông cá nhân** miễn phí  
  - Gửi broadcast miễn phí tới toàn bộ người dùng đã quan tâm OA  

- **Đăng nhập bằng Zalo / SĐT + ZNS OTP**  
  - Đăng nhập nhanh bằng tài khoản Zalo  
  - Đăng ký / đăng nhập bằng SĐT, xác thực qua ZNS OTP  

## Yêu cầu

- Zalo Official Account (Doanh nghiệp)  
- Tài khoản OA đã nâng cao, có quyền gửi ZNS & API “Quản lý người dùng”  

## Hướng dẫn cài đặt

1. Tải plugin vào thư mục `wp-content/plugins/devvn-zalo-oa`  
2. Kích hoạt plugin từ trang **Plugins** trên WordPress  
3. (Nếu có IonCube) Kích hoạt IonCube trước khi active plugin để tránh lỗi  

## Hướng dẫn cấu hình

### 1. Cấp quyền ứng dụng
1. Truy cập [Zalo OA Developers](https://developers.zalo.me/)  
2. Chọn Official Account → Cài đặt ứng dụng → Cấp quyền API “Tin nhắn” & “Quản lý người dùng”  

### 2. Cấu hình ZNS Template
- Vào menu **Zalo OA → ZNS Templates**  
- Chọn mẫu tin cho các sự kiện:  
  - Đơn hàng mới  
  - Thay đổi trạng thái  
  - Đơn hoàn thành  

### 3. Cấu hình Tin giao dịch
- Vào **Zalo OA → Transactional Messages**  
- Tùy chỉnh nội dung, nút kêu gọi hành động (CTA) cho từng sự kiện  

## Quản lý và báo cáo

- **Quản lý tin đã gửi**: Xem lịch sử mọi tin ZNS & giao dịch  
- **Danh sách số điện thoại**: Thống kê số đã nhận tin giao dịch  
- **Resend tin lỗi**: Tự động hoặc thủ công gửi lại tin lỗi  

## Tin nhắc đánh giá đơn hàng

- Vào **Zalo OA → Order Reviews**  
- Đặt số ngày sau khi hoàn thành đơn để gửi nhắc đánh giá  
- Khách đánh giá xong, đánh giá sẽ được đẩy về đúng sản phẩm trên website  

## Chiến dịch truyền thông cá nhân

- Vào **Zalo OA → Broadcast Campaign**  
- Tạo và lên lịch chiến dịch gửi tin miễn phí tới toàn bộ follower  

## Đăng nhập khách hàng

- **Đăng nhập qua Zalo**: Hiển thị nút `[zalo_login_btn]` bất kỳ đâu  
- **Đăng nhập / Đăng ký qua SĐT + ZNS OTP**: Xác thực nhanh qua Zalo  

---

## Lịch sử phiên bản (Changelog)

| Version   | Ngày        | Nội dung cập nhật                                                                          |
|-----------|-------------|--------------------------------------------------------------------------------------------|
| **1.2.7** | 22/01/2025  | - Thêm nút tạo table<br> - Khắc phục lỗi khi chưa kích hoạt IonCube                         |
| **1.2.6** | 10/01/2025  | - Cập nhật link lấy thông tin mẫu ZNS                                                      |
| **1.2.5** | 20/12/2024  | - Cập nhật chức năng gửi tin truyền thông V3                                               |
| **1.2.4** | 14/11/2024  | - Thêm thông báo lỗi qua mail khi gửi ZNS bị lỗi<br>- Fix reCAPTCHA tương thích WP 6.7.0   |
| **1.2.3** | 29/10/2024  | - Fix lịch gửi tin nhắc đánh giá<br>- Thêm đăng nhập SĐT qua ZNS OTP (YouTube demo)        |
| **1.2.2** | 05/09/2024  | - Fix giá trị ngày tạo đơn trong tin ZNS                                                   |
| **1.2.1** | 04/09/2024  | - Fix giá trị ngày tạo đơn trong tin ZNS                                                   |
| **1.2.0** | 26/07/2024  | - Cập nhật hàm tính thời gian gửi ZNS<br>- Thêm lựa chọn “Hình thức thanh toán”            |
| **1.1.9** | 12/07/2024  | - Fix mất Access Token khi bật Redis cache                                                 |
| **1.1.8** | 09/07/2024  | - Update encode tương thích PHP 8.2                                                        |
| **1.1.7** | 12/06/2024  | - Thêm filter `skip_send_zns_on_change_status`<br>- Update API “Quản lý người dùng”       |
| **1.1.6** | 12/05/2024  | - Thêm 2 trường hợp gửi ZNS khi thay đổi trạng thái                                       |
| **1.1.5** | 23/01/2024  | - Thêm đăng nhập bằng Zalo<br>- Shortcode `[zalo_login_btn]`                               |
| **1.1.4** | 18/01/2024  | - Hỗ trợ biến trong text của tin giao dịch                                                 |
| **1.1.3** | 04/01/2024  | - Loại bỏ tính năng nhắc cấp lại quyền sau 30 ngày                                         |
| **1.1.2** | 30/11/2023  | - Tối ưu code để tương thích addon                                                         |
| **1.1.1** | 28/11/2023  | - Tối ưu lịch gửi tin nền                                                                  |
| **1.1.0** | 12/10/2023  | - Thêm text mặc định cho note<br>- [NGHIÊM TRỌNG] Fix nội dung gửi tin trong chiến dịch      |
| **1.0.9** | 09/09/2023  | - Fix cảnh báo<br>- Thêm gửi ZNS tới admin OA (miễn phí ở chế độ develop)                  |
| **1.0.8** | 27/07/2023  | - Lấy danh sách follower<br>- Xem chi tiết data gửi đi & resend tin lỗi<br>- Lên lịch broadcast |
| **1.0.7** | 26/06/2023  | - Fix gửi tin đầu số `084`                                                                  |
| **1.0.6** | 20/06/2023  | - Fix urlencode link chi tiết đơn hàng<br>- Đếm lại số đánh giá cập nhật từ Zalo          |
| **1.0.5** | 20/06/2023  | - Fix khung giờ gửi ZNS (06:00–22:00)                                                       |
| **1.0.4** | 18/06/2023  | - Fix lỗi thiếu tên khách đánh giá<br>- Thêm biến `{order_total_view}`                     |
| **1.0.3** | 16/06/2023  | - Fix tham số `product_name` trong ZNS<br>- Thêm xử lý gửi tin nền                          |
| **1.0.1** | 13/06/2023  | - Tối ưu core<br>- Thêm `<note>`, `<phone_number>`, `<address>` cho ZNS                     |
| **1.0.0** | 12/06/2023  | - Ra mắt plugin                                                                             |

---

## Liên hệ & Hỗ trợ
- GitHub Issues: https://github.com/thanhan92-f1/dev-zalo-oa-hitechcloud
- Email: support@photuesoftware.vn  

---

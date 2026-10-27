# YouTube Lite (Android 5+)

Starter project Java không dùng thư viện giao diện ngoài. Tối ưu tương đối cho máy yếu bằng UI đơn giản và chỉ lấy tối đa 15 kết quả mỗi lượt.

## Tính năng trong bản mẫu
- Tìm kiếm video bằng YouTube Data API v3.
- Danh sách tiêu đề, kênh và mô tả ngắn.
- Mở video bằng ứng dụng YouTube hoặc trình duyệt đã cài.
- Nút đăng nhập mở YouTube chính thức để người dùng tự đăng nhập.
- minSdk 21 (Android 5.0).

## Giới hạn quan trọng
- Đây không phải ứng dụng YouTube chính thức.
- Video được phát ở ứng dụng YouTube/trình duyệt bên ngoài; toàn màn hình được xử lý ở đó. Bản mẫu không tự giải mã hoặc tải luồng video.
- Nút đăng nhập mở YouTube chính thức; không lấy mật khẩu, cookie hay token của người dùng.
- Cần API key để tìm kiếm. YouTube Data API có hạn mức và chính sách riêng.
- Không thể cam kết tìm kiếm/phát video trên mọi thiết bị Android 5; phải kiểm thử trên thiết bị thật.
- Không đặt API key dùng chung vào ứng dụng công khai. Hạn chế key theo API và ứng dụng nếu có thể; key nhúng trong APK có thể bị trích xuất.

## Cấu hình API key
1. Mở Google Cloud Console và tạo project.
2. Bật YouTube Data API v3.
3. Tạo API key.
4. Dán key vào ô trong ứng dụng khi chạy. Không cần sửa mã nguồn.
5. Nếu nhận lỗi `API key not valid`, `accessNotConfigured` hoặc `quotaExceeded`, kiểm tra key, API đã bật và hạn mức.

Tài liệu chính thức:
- https://developers.google.com/youtube/v3/docs/search/list
- https://developers.google.com/youtube/v3/getting-started

## Build trên điện thoại
AndroidIDE đã bị lưu trữ/không còn được duy trì chính thức; chỉ dùng nếu chấp nhận rủi ro tương thích. Hãy kiểm tra phiên bản hiện tại và nguồn tải tin cậy trước khi cài.
1. Giải nén ZIP vào bộ nhớ trong.
2. Mở dự án `OldYouTubeLite` bằng IDE hỗ trợ Gradle trên Android.
3. Cài SDK platform 33, Build Tools tương thích, JDK 11.
4. Đồng bộ Gradle; cấu hình dùng Android Gradle Plugin 7.4.2 và Gradle 7.5/7.6.
5. Chạy `:app:assembleDebug` hoặc chọn Build APK trong IDE.
6. APK debug thường nằm tại `app/build/outputs/apk/debug/app-debug.apk`.
7. Cài APK trên thiết bị thử nghiệm. Nếu lỗi build, ghi lại toàn bộ thông báo lỗi.

## Kiểm thử thực tế
- Cài đặt và khởi chạy trên Android 5.0/5.1 và các bản Android mục tiêu.
- Thử tìm kiếm từ khóa tiếng Việt, từ khóa dài, và từ khóa không có kết quả.
- Thử khi mất mạng, API key sai, API chưa bật và hết hạn mức.
- Mở video và xác nhận ứng dụng YouTube/trình duyệt có phát được không.
- Thử toàn màn hình trong trình phát bên ngoài.
- Thử đăng nhập trực tiếp trong ứng dụng YouTube/trình duyệt; bản mẫu không tự đăng nhập thay người dùng.
- Kiểm tra RAM, độ trễ, xoay màn hình và đóng/mở lại ứng dụng.

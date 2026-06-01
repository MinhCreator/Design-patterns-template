# Design-patterns-template
Design pattern Dev need to know
### NHÓM KHỞI TẠO (CREATIONAL PATTERNS)
📌 SINGLETON PATTERN
- Lợi ích: Ngăn chặn việc tạo ra quá nhiều đối tượng trùng lặp gây lãng phí tài nguyên và xung đột dữ liệu, đảm bảo trong suốt hệ thống chỉ có duy nhất một đối tượng tồn tại.
- Ứng dụng thực tế: Giống như Bộ quản lý kết nối Database (Database Connection Pool). Cả hệ thống chỉ dùng chung một lối vào duy nhất để đọc/ghi dữ liệu, tránh việc mỗi tính năng tự mở một kết nối riêng gây quá tải và làm sập server.
📌 BUILDER PATTERN
- Lợi ích: Giúp tách nhỏ quá trình khởi tạo các đối tượng phức tạp thành từng bước rõ ràng. Bạn không còn phải đau đầu với những hàm khởi tạo chứa quá nhiều tham số, dễ nhầm lẫn và khó bảo trì.
- Ứng dụng thực tế: Giống như công cụ Query Builder khi truy vấn dữ liệu. Thay vì viết một chuỗi code dài phức tạp, bạn được lắp ráp từng phần như .select(), .where(), .orderBy(); phần nào không dùng đến thì chỉ việc bỏ qua.
📌 FACTORY PATTERN
- Lợi ích: Gom toàn bộ logic khởi tạo đối tượng vào một nơi duy nhất. Code chính của bạn sẽ sạch sẽ hơn rất nhiều vì không còn những câu lệnh if-else lặp đi lặp lại để kiểm tra xem cần tạo ra loại đối tượng nào.
- Ứng dụng thực tế: Giống như Hệ thống tích hợp cổng thanh toán. Khi khách chọn "Momo", "ZaloPay" hay "Stripe", Factory sẽ tự nhận diện và tạo ra đúng bộ xử lý của cổng thanh toán tương ứng, giúp giấu đi toàn bộ phần code cấu hình phức tạp ở bên dưới.
------
### NHÓM CẤU TRÚC (STRUCTURAL PATTERNS)
📌 FACADE PATTERN
- Lợi ích: Cung cấp một giao diện đơn giản để che đi hệ thống phức tạp bên dưới. Các module khác chỉ cần gọi một vài hàm cơ bản từ lớp Facade này là xong, thay vì phải tự tay thao tác với hàng loạt lớp con cồng kềnh phía sau.
- Ứng dụng thực tế: Giống như Hệ thống đặt hàng trên các trang thương mại điện tử. Khi khách bấm nút "Đặt hàng", Facade sẽ tự chạy hàng loạt tác vụ bên dưới: cập nhật tồn kho, tạo hóa đơn, trừ tiền và gọi bên vận chuyển, giúp code chính không bị rối.
📌 ADAPTER PATTERN
- Lợi ích: Giúp hai hệ thống hoặc thư viện có chuẩn dữ liệu hoàn toàn khác biệt vẫn có thể kết nối và làm việc mượt mà với nhau. Bạn có thể thoải mái tích hợp công nghệ mới vào dự án mà không sợ làm ảnh hưởng hay phải đập đi xây lại phần code cũ đang chạy ổn định.
- Ứng dụng thực tế: Khi bạn sài một thư viện vẽ Biểu đồ mới vào dự án. Data cũ của bạn lưu ngày tháng dạng Chuỗi ("2026-05-30"), nhưng thư viện biểu đồ yêu cầu dùng dạng Số timestamp (1780104000). Thay vì sửa data, bạn dùng Adapter ở giữa để tự động đổi Chuỗi thành Số rồi truyền vào biểu đồ. Thư viện mới hoạt động ngay mà data cũ không cần thay đổi.
------
### NHÓM HÀNH VI (BEHAVIORAL PATTERNS)
📌 STRATEGY PATTERN
- Lợi ích: Thay vì viết một hàm chứa đầy if-else phức tạp, bạn tách mỗi cách xử lý thành một "chiến thuật" độc lập. Khi ứng dụng chạy, tùy tình huống mà hệ thống sẽ tự động chọn đúng "chiến thuật" phù hợp, giúp code gọn gàng và cực kỳ dễ thêm tính năng mới.
- Ứng dụng thực tế: Tính năng tính Mã giảm giá khi mua hàng. Tùy loại mã bạn nhập, app sẽ tự động chọn đúng công thức tương ứng để tính tiền: Giảm theo %, Giảm số tiền cố định (ví dụ: giảm 50k), hoặc Freeship.
📌 OBSERVER PATTERN
- Lợi ích: Tạo ra cơ chế tự động cập nhật và đồng bộ thông tin giữa các đối tượng. Khi một thành phần thay đổi trạng thái, tất cả các bên liên quan đăng ký theo dõi sẽ lập tức nhận được thông báo, giúp hệ thống hoạt động tối ưu mà không tốn tài nguyên chạy vòng lặp đi kiểm tra liên tục.
- Ứng dụng thực tế: Tính năng Đăng ký nhận thông báo khi sản phẩm có hàng. Thay vì bạn phải ngày nào cũng truy cập vào website để kiểm tra xem món đồ mình thích đã về hàng chưa, bạn chỉ cần để lại email. Khi kho cập nhật số lượng lớn hơn 0, hệ thống sẽ tự động gửi email thông báo cho bạn và tất cả những người khác cùng lúc.

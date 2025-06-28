# 🎮 Hollow Knight Online - 2D Metroidvania Platformer

- 🎯 **Được giảng viên đánh giá 10 điểm bới Ph.D. Nguyen Trinh Dong UIT** vì xử lý **tình huống vật lý đặc biệt ngay trên lớp**:  
  Khi nhân vật nhảy từ dưới lên vào platform, làm quái vật **Tiktik** rơi xuống đúng như behavior trong game gốc *Hollow Knight*.
- Dự án này là một game 2D thuộc thể loại **Metroidvania Platformer** lấy cảm hứng từ *Hollow Knight*, được phát triển trong khuôn khổ môn học **Công nghệ .NET** tại Trường Đại học Công nghệ Thông tin. Game nổi bật với tính năng **chơi trực tuyến nhiều người chơi**. Báo cáo chi tiết ở link này: https://docs.google.com/document/d/1w4wfIoQd9pejM34C5aM14S3KNNMVvALQmUutFJNOFow/edit?tab=t.0

## 1. 🧭 Tổng quan về Dự án

Game phiêu lưu hành động 2D nơi người chơi khám phá thế giới mở, giải đố, và chiến đấu với các kẻ thù. Kết hợp công nghệ hiện đại như:

- **SignalR** để chơi nhiều người.
- **ASP.NET Core** để quản lý người dùng và dữ liệu.

### 🔑 Tính năng chính:

- **Lối chơi Metroidvania 2D:** Khám phá thế giới mở, vượt chướng ngại vật, giải đố và chiến đấu.
- **Chơi nhiều người (Online):** Tối đa 4 người chơi kết nối và chơi cùng nhau trong 1 phòng.
- **Quản lý người dùng:** Đăng ký, đăng nhập, tạo phòng qua ASP.NET Core.
- **Tiến trình nhân vật:** Hệ thống chiến đấu, nâng cấp kỹ năng và vũ khí.
- **Bảng quản trị (Admin Panel):** Web riêng để quản lý tài khoản người chơi.

## 2. 🕹️ Lối Chơi Cốt Lõi

Người chơi khám phá các khu vực trong Hallownest, chiến đấu với quái vật để thu thập:

- **Geo:** Tiền tệ trong game.
- **Soul:** Dùng để hồi máu hoặc thi triển kỹ năng đặc biệt.

Khi chết, người chơi mất Geo và có thể lấy lại bằng cách đánh bại **Shade** của chính mình.

## 3. 🧱 Kiến trúc Hệ thống

Hệ thống hoạt động theo mô hình **Client-Server**:

- **Client:** Unity game – điều khiển nhân vật, gửi hành động tới server.
- **Server:** ASP.NET Core – xử lý logic game, đồng bộ hóa trạng thái nhiều người chơi.
- **Database:** Lưu người dùng, điểm số, kỹ năng, trạng thái game.

### Thành phần chính:

- **Game Logic:** Điều khiển hành vi nhân vật, kẻ thù, tương tác.
- **Xác thực & Ủy quyền:** Đảm bảo truy cập an toàn.
- **SignalR:** Giao tiếp thời gian thực giữa client & server.

## 4. 🛠️ Công nghệ Sử dụng

| Thành phần            | Công nghệ           |
|-----------------------|----------------------|
| Game Engine           | Unity                |
| Multiplayer Online    | SignalR              |
| Backend Server        | ASP.NET Core         |
| Authentication        | ASP.NET Identity     |
| UI Web Admin          | ASP.NET MVC          |

Giảng viên hướng dẫn: **Nguyễn Trịnh Đông**

## 5. 🧍 Các Đối tượng & Yếu tố trong Game

### 🔍 Người chơi

- Di chuyển, nhảy, ngã, tấn công.
- Mất máu khi va chạm kẻ thù.
- Vũ khí mặc định: **Nail** (25 sát thương).

### 👾 Kẻ Thù

| Loại | Ví dụ |
|------|-------|
| Không đuổi theo | Crawlid, Tiktik |
| Đuổi theo | Husk Hornhead, Vengefly, Husk Guard |

### 🌿 Môi trường

- **Cỏ:** Có thể cắt.
- **Cột đá:** Cắt được, gây hiệu ứng rung.
- **HealBar:** Hồi mana và máu.

### 💥 Hiệu ứng

- Va chạm đá, bụi, máu, hiệu ứng mana, sóng năng lượng, bóng tối, thay đổi màu khu vực.
- Kỹ năng đặc biệt từ quái như Husk Guard (đập đất, shockwave).

## 6. ⚙️ Kỹ Thuật và Thiết Kế

- **Singleton:** Dùng cho camera, manager các hệ thống.
- **Parallax:** Tạo chiều sâu bản đồ với nhiều lớp nền.
- **Tilemap:** Thiết kế bản đồ dạng nhiều lớp.
- **Shader:** Tạo hiệu ứng sóng, ánh sáng, máu.
- **Camera:** 3 chế độ di chuyển (theo nhân vật, cố định trục Y, cố định hoàn toàn).
- **Va chạm:** Rung màn hình, hiệu ứng vật lý khi bị đánh.
- **Hoạt ảnh:** Sử dụng hệ thống Animator cho nhân vật, kẻ thù, môi trường.
- **Âm thanh:** Gắn với hành động và môi trường (cắt cỏ, đánh đá, tấn công).
- **Giao diện:** UI đăng nhập, đăng ký, menu chính, bảng xếp hạng, chọn phòng.

## 7. 📊 Đánh Giá & Phân Công

### ✅ Điểm mạnh:

- Tái tạo gameplay phức tạp của Hollow Knight.
- Thiết kế nhân vật và bản đồ mượt mà.
- Ánh sáng, hiệu ứng và camera hoạt động tốt.
- Kết nối online thành công.

### ❌ Cần cải thiện:

- Một số hiệu ứng và kỹ năng chưa hoàn chỉnh.
- Chưa hoàn thiện gameplay 2 người chơi.
- Một số mã chưa được tối ưu.

### 🔧 Đã hoàn thành:

- Map “Forgotten” hoàn chỉnh.
- Map “King’s Pass” gần xong.
- Hệ thống hiệu ứng, ánh sáng, âm thanh.
- Kết nối online ổn định và thành công.
- Điều khiển nhân vật mượt mà.

### ❌ Chưa hoàn thành:

- Nâng cấp vũ khí, kỹ năng.
- Một số map và quái vật khác.
- Một số hiệu ứng của bản gốc.
- Chưa hoàn thiện gameplay 2 người chơi.

### 👨‍💻 Phân công công việc:

- **Võ Minh Kiệt** (22520727) – 100%
- **Hồng Chung Lâm** (22520737) – 100%

## 8. 📚 Tài Liệu Tham Khảo

- YouTube: Các video phân tích gameplay Hollow Knight
- [Hollow Knight Wiki trên Fandom](https://hollowknight.fandom.com)
- Reddit: Tập hợp toàn bộ sprite game Hollow Knight

---

## 💡 Ghi chú

> Game này **không phải sản phẩm thương mại** mà là bài tập môn học. Mọi tài nguyên gốc thuộc về nhóm phát triển *Team Cherry*.

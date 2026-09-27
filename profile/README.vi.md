[English](https://github.com/HandLive/.github/blob/main/profile/README.md) | Tiếng Việt

# HandLive

HandLive là dự án mã nguồn mở. Dự án đưa các tính năng native riêng trong từng hệ sinh thái, như Handoff trên Apple, lên Android. Máy Android đồng bộ với Mac, iPhone và iPad. Máy Apple đồng bộ ngược lại với Android. Mã hóa đầu-cuối luôn bật. Relay không đọc nội dung. Giấy phép Apache 2.0. Có tiếng Anh (mặc định) và tiếng Việt.

Phương châm: *WebSocket cho dữ liệu, Bluetooth cho giọng nói.*

<p>
<img src="https://raw.githubusercontent.com/HandLive/handlive/main/docs/screenshots/android/04-devices-connected.vi.png" alt="Android" height="360">
<img src="https://raw.githubusercontent.com/HandLive/handlive/main/docs/screenshots/ios/04-sms-conversation.vi.png" alt="iPhone" height="360">
<img src="https://raw.githubusercontent.com/HandLive/handlive/main/docs/screenshots/macos/04-incoming-call-panel.vi.png" alt="Mac" height="240">
</p>

[Xem thêm ảnh màn hình](https://github.com/HandLive/handlive/blob/main/docs/screenshots/README.vi.md)

| Kho | Vai trò | Ngôn ngữ |
|-----|---------|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub tài liệu: đặc tả, kế hoạch và design system. **Bắt đầu từ đây.** | Markdown, Python |
| [handlive-android](https://github.com/HandLive/handlive-android) | Ứng dụng trên điện thoại Android. Thực thi Handoff và các tính năng continuity | Kotlin |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Ứng dụng Mac, iPhone và iPad. Nhận dữ liệu từ Android và gửi ngược lại | Swift |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Máy chủ chuyển tiếp khi các máy không cùng mạng. Không đọc nội dung | Rust |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Test vector, JSON Schema, design token và chuỗi giao diện dùng chung | JSON, Python |

| Tính năng | macOS | iOS/iPadOS |
|-----------|:-----:|:----------:|
| Bảng nhớ tạm hai chiều | ✅ | ✅ |
| SMS nhận/gửi | ✅ | ✅ |
| Thông tin và điều khiển cuộc gọi | ✅ | ✅ (không âm thanh) |
| Nghe gọi trên máy (Bluetooth HFP, dự phòng Opus/WebSocket) | ✅ | ❌ |
| Camera và micro ảo cho ứng dụng họp | ✅ | ❌ |

**Trạng thái:** Phase 1 (đồng bộ clipboard giữa Android và Mac) và Phase 2 (SMS, ứng dụng iPhone và iPad, relay và thông báo đẩy) đã gộp vào `main`. Cổng G1 (kiểm trên máy thật) và cổng G2 (Play Console) vẫn còn mở, nên chưa có bản phát hành. Phase 3 đang làm: thông tin và điều khiển cuộc gọi. Lộ trình: [docs/project-roadmap.vi.md](https://github.com/HandLive/handlive/blob/main/docs/project-roadmap.vi.md).

Đóng góp: [CONTRIBUTING](https://github.com/HandLive/.github/blob/main/CONTRIBUTING.vi.md) · Bảo mật: [SECURITY](https://github.com/HandLive/.github/blob/main/SECURITY.vi.md) · Ứng xử: [CODE_OF_CONDUCT](https://github.com/HandLive/.github/blob/main/CODE_OF_CONDUCT.vi.md)

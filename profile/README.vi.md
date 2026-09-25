[English](https://github.com/HandLive/.github/blob/main/profile/README.md) | Tiếng Việt

# HandLive

Điện thoại Android là điểm trung chuyển. Nó đưa clipboard, SMS, cuộc gọi kèm âm thanh, camera và mic sang macOS. iPhone và iPad nhận clipboard, SMS và thông tin cuộc gọi. Mã hóa đầu-cuối luôn bật. Relay không đọc nội dung. Mã nguồn mở, Apache License 2.0. Có tiếng Anh (mặc định) và tiếng Việt.

Phương châm: *WebSocket cho dữ liệu, Bluetooth cho giọng nói.*

| Kho | Vai trò | Ngôn ngữ |
|-----|---------|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub tài liệu, kế hoạch và design system. **Bắt đầu từ đây.** | Markdown, Python |
| [handlive-android](https://github.com/HandLive/handlive-android) | Ứng dụng trên điện thoại, hub của hệ thống | Kotlin |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Ứng dụng Mac, iPhone và iPad | Swift |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Máy chủ chuyển tiếp, không đọc nội dung | Rust |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Test vector, JSON Schema, design token, chuỗi giao diện dùng chung | JSON, Python |

| Tính năng | macOS | iOS/iPadOS |
|-----------|:-----:|:----------:|
| Bảng nhớ tạm hai chiều | ✅ | ✅ |
| SMS nhận/gửi | ✅ | ✅ |
| Thông tin và điều khiển cuộc gọi | ✅ | ✅ (không âm thanh) |
| Nghe gọi trên máy (Bluetooth HFP, dự phòng Opus/WebSocket) | ✅ | ❌ |
| Camera và micro ảo cho ứng dụng họp | ✅ | ❌ |

**Trạng thái:** Phase 0 đã xong (khung, giao thức, mã hóa, token, CI). Chưa có tính năng cho người dùng. Bước tiếp theo là Phase 1, đồng bộ clipboard giữa Android và Mac. Lộ trình: [docs/project-roadmap.md](https://github.com/HandLive/handlive/blob/main/docs/project-roadmap.md).

Đóng góp: [CONTRIBUTING](https://github.com/HandLive/.github/blob/main/CONTRIBUTING.vi.md) · Bảo mật: [SECURITY](https://github.com/HandLive/.github/blob/main/SECURITY.vi.md) · Ứng xử: [CODE_OF_CONDUCT](https://github.com/HandLive/.github/blob/main/CODE_OF_CONDUCT.vi.md)

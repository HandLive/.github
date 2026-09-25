# HandLive

**Điện thoại Android làm hub — bảng nhớ tạm, SMS, cuộc gọi (kèm âm thanh) và camera/micro — cho Mac, iPhone và iPad.** Mã hóa đầu cuối không thể tắt, relay zero-knowledge, mã nguồn mở theo Apache License 2.0.

*An Android phone as the hub for clipboard, SMS, calls (with live audio) and camera/mic on macOS, iOS and iPadOS — end-to-end encrypted, zero-knowledge relay, open source under Apache-2.0.*

Phương châm thiết kế: *WebSocket cho dữ liệu, Bluetooth cho giọng nói.*

| Kho | Vai trò | Ngôn ngữ |
|-----|---------|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub: tài liệu thiết kế (hợp đồng cho mọi mã), kế hoạch, design system — **bắt đầu từ đây** | Markdown, Python |
| [handlive-android](https://github.com/HandLive/handlive-android) | Ứng dụng Android (hub điện thoại) | Kotlin |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Ứng dụng macOS và iOS/iPadOS | Swift |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Cloud relay zero-knowledge | Rust |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Test vector, JSON Schema, design tokens dùng chung | JSON, Python |

| Tính năng | macOS | iOS/iPadOS |
|-----------|:-----:|:----------:|
| Bảng nhớ tạm hai chiều | ✅ | ✅ |
| SMS nhận/gửi | ✅ | ✅ |
| Thông tin và điều khiển cuộc gọi | ✅ | ✅ (không âm thanh) |
| Nghe gọi trên máy (Bluetooth HFP, dự phòng Opus/WebSocket) | ✅ | ❌ |
| Camera và micro ảo cho ứng dụng họp | ✅ | ❌ |

**Trạng thái:** Phase 0 (khung, giao thức, mã hóa, token, CI) đã xong; Phase 1 — đồng bộ bảng nhớ tạm Android ↔ Mac — là bước tiếp theo. Lộ trình: [docs/project-roadmap.md](https://github.com/HandLive/handlive/blob/main/docs/project-roadmap.md).

Đóng góp: [CONTRIBUTING](https://github.com/HandLive/.github/blob/main/CONTRIBUTING.md) · Bảo mật: [SECURITY](https://github.com/HandLive/.github/blob/main/SECURITY.md) · Ứng xử: [CODE_OF_CONDUCT](https://github.com/HandLive/.github/blob/main/CODE_OF_CONDUCT.md)

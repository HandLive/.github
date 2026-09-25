[English](SECURITY.md) | Tiếng Việt

# Chính sách bảo mật

HandLive xử lý bảng nhớ tạm, SMS, cuộc gọi và camera của người dùng với mã hóa đầu cuối; lỗi bảo mật được ưu tiên cao nhất.

## Báo cáo lỗ hổng

- Không mở issue công khai.
- Dùng **Report a vulnerability** (tab Security) trên kho liên quan, hoặc email me@hxd.vn.
- Gửi kèm: kho và commit, nền tảng, các bước tái hiện, tác động, PoC nếu có.

## Cam kết

- Xác nhận đã nhận trong 7 ngày; cập nhật tiến độ ít nhất mỗi 14 ngày.
- Công bố phối hợp: vá trước, công bố sau — tối đa 90 ngày kể từ khi nhận, sớm hơn nếu vá xong.
- Ghi công người báo cáo trong ghi chú phát hành nếu họ muốn. Chưa có chương trình thưởng.

## Phạm vi

Mọi kho của org HandLive: mã hóa và ghép nối (XChaCha20-Poly1305, X25519, HKDF, QR/PIN), giao thức WebSocket, relay zero-knowledge, quyền và dữ liệu trên thiết bị, CI và chuỗi cung ứng. Ngoài phạm vi: lỗ hổng của hệ điều hành hay thư viện bên thứ ba (báo cho họ; báo chúng tôi nếu ảnh hưởng HandLive), tấn công cần thiết bị đã root hoặc jailbreak.

## Phiên bản hỗ trợ

Dự án đang ở Phase 0, chưa phát hành. Khi phát hành: nhánh `main` và phiên bản mới nhất của mỗi kho.

# Đóng góp cho HandLive

*English summary at the end.*

HandLive là dự án mã nguồn mở theo Apache License 2.0, gồm năm kho làm việc trong **một workspace**:

| Kho | Nội dung |
|-----|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub: tài liệu thiết kế chi tiết (hợp đồng cho mọi mã), kế hoạch, design system, công cụ tài liệu — **đọc trước** |
| [handlive-android](https://github.com/HandLive/handlive-android) | Ứng dụng Android (Kotlin, Gradle) |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Ứng dụng macOS và iOS/iPadOS (Swift) |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Cloud relay zero-knowledge (Rust) |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Test vector, JSON Schema, design tokens dùng chung |

## Chuẩn bị workspace

```sh
git clone git@github.com:HandLive/handlive.git HandLive && cd HandLive
tools/workspace.sh clone git@github.com:HandLive   # clone các kho còn lại vào android/, apple/, relay/, shared/
tools/workspace.sh hooks                            # bật hook commit của dự án
```

Bố cục này là bắt buộc: build và test đọc `../shared`, test Apple và công cụ schema đọc `../docs`. Lệnh build/test từng kho: `docs/codebase-summary.md` của hub và `README.md` của kho.

## Quy trình

1. Mở issue (mẫu có sẵn) hoặc nhận một thẻ việc trong `plans/20260925-implementation/` của hub.
2. Tài liệu là hợp đồng giữa các nền tảng: đổi giao thức, mã lỗi, chuỗi giao diện thì sửa `docs/detailed-design/` trước (`python3 tools/docs/validate_design_docs.py` phải in `problems=0`), rồi `shared/` (vector, schema), rồi mã nền tảng.
3. Nhánh `feat/<slug>` hoặc `fix/<slug>` trong kho liên quan; PR vào `main` của kho đó. Sửa `shared/` thì PR ở handlive-shared trước, nêu rõ để các nền tảng khác chạy lại test.
4. Test xanh trước khi mở PR; CI dựng lại đúng bố cục workspace.

## Commit

- Conventional Commits, tiếng Anh, ngắn: `feat(android): …`, `fix(relay): …`, `test(apple): …`, `docs: …`.
- Nhỏ và sớm: mỗi bước hợp lý một commit (khung → module → test → tài liệu); một commit không trải hai kho.
- Đứng tên người thật và ký DCO: `git commit -s` thêm `Signed-off-by: Tên <email>`, xác nhận bạn có quyền đóng góp theo [Developer Certificate of Origin](https://developercertificate.org). Không ghi công cụ AI làm tác giả hay đồng tác giả — hook `.githooks/commit-msg` và job CI `commit-policy` từ chối.
- Không commit secret, khóa, chứng chỉ, dotenv, file sinh của IDE hay build.

## Ngôn ngữ và giao diện

- Tài liệu, kế hoạch, báo cáo, chuỗi giao diện: tiếng Việt có dấu (dấu kiểu Apple: hóa, xóa, hủy, tùy). Mã, commit, mã lỗi: tiếng Anh.
- Chuỗi giao diện lấy nguyên văn từ tài liệu chi tiết; thành phần và token theo `docs/design-system/`.

## Phụ thuộc mới

Chỉ giấy phép tương thích Apache-2.0: Apache, MIT, BSD, ISC, MPL-2.0, OFL (font). Không GPL, LGPL, AGPL. Tài nguyên bên thứ ba đóng gói trong app ghi vào `NOTICE` của kho.

## Bảo mật

Không mở issue công khai cho lỗ hổng — xem [SECURITY.md](SECURITY.md).

## English summary

HandLive is Apache-2.0. Clone the hub and run `tools/workspace.sh clone` (the nested layout is required); the hub's docs are the contract — change them first, then `shared/`, then platform code. Small Conventional Commits under a real name with a DCO sign-off (`git commit -s`); never an AI tool as author or co-author. New dependencies must be Apache-2.0-compatible. Report vulnerabilities privately (SECURITY.md).

[English](CONTRIBUTING.md) | Tiếng Việt

# Đóng góp cho HandLive

HandLive là dự án mã nguồn mở theo Apache License 2.0. Dự án đưa các tính năng native riêng trong từng hệ sinh thái, như Handoff trên Apple, lên Android. Dự án gồm năm kho làm việc trong **một workspace**:

| Kho | Nội dung |
|-----|----------|
| [handlive](https://github.com/HandLive/handlive) | Hub tài liệu: thiết kế chi tiết (đặc tả cho mọi mã), kế hoạch, design system, công cụ tài liệu. **Đọc trước.** |
| [handlive-android](https://github.com/HandLive/handlive-android) | Ứng dụng trên điện thoại Android, thực thi Handoff và các tính năng continuity (Kotlin, Gradle) |
| [handlive-apple](https://github.com/HandLive/handlive-apple) | Ứng dụng Mac, iPhone và iPad, nhận dữ liệu từ Android và gửi ngược lại (Swift) |
| [handlive-relay](https://github.com/HandLive/handlive-relay) | Máy chủ chuyển tiếp khi các máy không cùng mạng, không đọc nội dung (Rust) |
| [handlive-shared](https://github.com/HandLive/handlive-shared) | Test vector, JSON Schema, design token và catalog chuỗi giao diện dùng chung |

## Chuẩn bị workspace

```sh
git clone git@github.com:HandLive/handlive.git HandLive && cd HandLive
tools/workspace.sh clone git@github.com:HandLive   # clone các kho còn lại vào android/, apple/, relay/, shared/
tools/workspace.sh hooks                            # bật hook commit của dự án
```

Bố cục này là bắt buộc: build và test đọc `../shared`, test Apple và công cụ schema đọc `../docs`. Lệnh build/test từng kho: `docs/codebase-summary.md` của hub và `README.md` của kho.

## Quy trình

1. Mở issue (mẫu có sẵn) hoặc nhận một thẻ việc trong `plans/20260925-implementation/` của hub.
2. Tài liệu là hợp đồng giữa các nền tảng: đổi giao thức, mã lỗi, chuỗi giao diện thì sửa `docs/detailed-design/` trước — cả `X.md` và `X.vi.md`; `python3 tools/docs/validate_design_docs.py` phải in `problems=0` và `python3 tools/docs/check_bilingual_docs.py` phải qua — rồi `shared/` (vector, schema, catalog chuỗi), rồi mã nền tảng.
3. Nhánh `feat/<slug>` hoặc `fix/<slug>` trong từng kho liên quan, cùng một tên nhánh ở mọi kho; CI lấy nhánh trùng tên của handlive-shared và hub nếu có. PR vào `main`; sửa `shared/` đi trước, nêu rõ để các nền tảng khác chạy lại test.
4. Test xanh trước khi mở PR; CI dựng lại đúng bố cục workspace.

## Commit

- Conventional Commits, tiếng Anh, ngắn: `feat(android): …`, `fix(relay): …`, `test(apple): …`, `docs: …`.
- Nhỏ và sớm: mỗi bước hợp lý một commit (khung → module → test → tài liệu); một commit không trải hai kho.
- Đứng tên người thật và ký DCO: `git commit -s` thêm `Signed-off-by: Tên <email>`, xác nhận bạn có quyền đóng góp theo [Developer Certificate of Origin](https://developercertificate.org). Không ghi công cụ AI làm tác giả hay đồng tác giả — hook `.githooks/commit-msg` và job CI `commit-policy` từ chối.
- Không commit secret, khóa, chứng chỉ, dotenv, file sinh của IDE hay build.

## Ngôn ngữ

- Sản phẩm đa ngôn ngữ: tiếng Anh (`en`) là ngôn ngữ mặc định, tiếng Việt (`vi`) là ngôn ngữ thứ hai. Mọi chuỗi giao diện có khóa ổn định trong `shared/strings/ui-strings.json` với đủ hai ngôn ngữ; mã không viết cứng câu chữ hiển thị. Chuỗi tiếng Anh theo văn phong tiếng Anh của Apple (viết hoa kiểu tiêu đề cho nút, menu, tiêu đề cửa sổ); chuỗi tiếng Việt bỏ dấu kiểu Apple (hóa, xóa, hủy, tùy).
- Tài liệu song ngữ: `X.md` tiếng Anh (bản chuẩn) và `X.vi.md` tiếng Việt, cùng cấu trúc, cập nhật trong cùng commit. Mã, thông điệp commit, mã lỗi, log và báo cáo công việc viết bằng tiếng Anh.

## Phụ thuộc mới

Chỉ giấy phép tương thích Apache-2.0: Apache, MIT, BSD, ISC, MPL-2.0, OFL (font). Không GPL, LGPL, AGPL. Ưu tiên thư viện không có thành phần độc quyền để app phân phối được cả ngoài kho ứng dụng. Tài nguyên bên thứ ba đóng gói trong app ghi vào `NOTICE` của kho.

## Bảo mật

Không mở issue công khai cho lỗ hổng — xem [SECURITY.vi.md](SECURITY.vi.md).

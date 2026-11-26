# LockIn: trang giới thiệu

Trang giới thiệu cho LockIn, ứng dụng hẹn cùng học cho sinh viên. Một bạn tạo buổi học, nhập email các bạn trong nhóm, và LockIn gửi email mời từng người. Máy nhắc trước giờ học, rồi điểm danh ai đúng giờ, ai trễ.

- Trang: https://lockin-4everyung.github.io/lockin-landing-page/
- Prototype Figma: https://www.figma.com/proto/7Vm0iAHHDj2LtIL7AGjpC7/LockIn_MobileApp?node-id=25-563&starting-point-node-id=25%3A563&page-id=7%3A3&scaling=scale-down
- File thiết kế: https://www.figma.com/design/7Vm0iAHHDj2LtIL7AGjpC7/LockIn_MobileApp?node-id=1020-20317

## Deploy lên GitHub Pages

Trang là HTML tĩnh: không cần build, không cần cài gì.

1. Vào **Settings → Pages** của repo.
2. Ở **Source**, chọn **Deploy from a branch**, nhánh `main`, thư mục `/ (root)`, rồi bấm **Save**.
3. Chờ khoảng một phút rồi mở link trang ở trên.

File `.nojekyll` để GitHub Pages phục vụ nguyên các file, không chạy Jekyll.

## Xem trên máy

Phải mở qua server, vì trang tải script dạng module. Mở bằng `file://` sẽ không chạy.

```bash
python -m http.server 8000
```

Rồi mở http://localhost:8000/.

## Cấu trúc

- `index.html`: toàn bộ trang (chữ, CSS và script riêng của trang).
- `assets/screens/`: ảnh màn xuất từ Figma; tên người và email trong ảnh là dữ liệu mẫu.
- `assets/`: phần còn lại là bộ thư viện giao diện (hệ thống, chuyển động, sơ đồ, icon).
- `share.jpg`: ảnh xem trước khi chia sẻ link.

Repo chỉ chứa các file trang dùng. `.gitignore` liệt kê đích danh từng file trong `assets/`. Nếu thêm file mới vào `assets/` thì phải thêm một dòng `!/assets/...` tương ứng, không thì git bỏ qua.

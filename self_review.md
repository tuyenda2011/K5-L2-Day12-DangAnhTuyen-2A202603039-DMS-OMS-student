# Tự đánh giá — Đặng Anh Tuyền · G03

## Rà soát 4 cảnh

Các mục dưới đây dựa trên báo cáo lần đầu trong `check_cpAB.txt`, báo cáo cuối và dữ liệu nhãn trong `export_final.zip`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb | `object`, `infant_seat` | `seat_flip` | Lần đầu `object` để `driver`, hai loại ghế trẻ em trùng `rear_right`. Bản cuối ghi túi `rear_middle`, nôi `rear_left` và ghế trẻ em `rear_right`. | Có, đã đối chiếu bản xuất cuối. |
| S02_ir | `child_seat` | `seat_flip` | Lần đầu giữ mặc định `driver`. Bản cuối ghi `rear_right`. | Có, đã đối chiếu bản xuất cuối. |
| D03 | `face`, `face13` | `flag` | Lần đầu trạng thái mắt và cờ điểm không khớp. Bản cuối ghi mắt trái `open`, mắt phải `unknown`, bốn điểm mắt phải đều `outside`. | Có, cảnh báo đã hết. |
| D05 | `face13` | `ok` | Checker cảnh báo theo x. Tọa độ y của khóe ngoài mắt trái là 669.12, lớn hơn 517.65 của mắt phải, phù hợp ảnh D xoay 90°. | Giữ nguyên quy ước trái/phải theo y. |

## Lỗi lặp lại và cách tránh

Lỗi lặp lại trong báo cáo đầu là để `seat = driver` cho đồ vật hoặc ghế trẻ em ở hàng ghế sau. Sau mỗi box OMS, kiểm tra ngay thuộc tính `seat` và đối chiếu với vị trí theo xe. Trước khi lưu, rà lại bảng Objects để phát hiện giá trị mặc định còn sót.

## Ghi chú review

Bản gốc có 0 lỗi và 1 cảnh báo ở `D05` theo `check_final.txt`. Nguyễn Chí Tài đã review và xác nhận cách gán hai khóe mắt theo trục y. Kết luận đã được ghi vào `disagreement_log.csv`.

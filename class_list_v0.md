# Danh sách lớp v0 — Đặng Anh Tuyền · G03

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `face` | Box mặt tài xế | Xác định vùng mặt để theo dõi mắt và hướng đầu. | Có nếu mặt đủ rõ. |
| 2 | `eye_left`, `eye_right` | `open`, `closed`, `unknown` | Theo dõi trạng thái từng mắt qua nhiều khung, phục vụ cảnh báo buồn ngủ. | Có khi thấy khe mắt hoặc mí. |
| 3 | `glasses` | `none`, `clear`, `sun`, `unknown` | Đánh giá khả năng quan sát mắt khi có kính hoặc phản xạ. | Tùy độ phản xạ và khả năng phân biệt tròng. |
| 4 | `gaze_zone` | `road`, `mirror_l`, `mirror_r`, `mirror_c`, `cluster`, `center`, `lap`, `other` | Xác định tài xế đang nhìn đường hay nhìn sang vùng khác. | Tùy độ rõ của mắt và hướng đầu. |
| 5 | `hand`, `on_wheel` | Box tay, `yes`, `no`, `unknown` | Xác định tay nào đang chạm vô lăng. | Có nếu nhìn thấy tay và điểm tiếp xúc. |
| 6 | `phone`, `state` | Box điện thoại, `held`, `mounted`, `lap` | Nhận biết tài xế đang cầm điện thoại hoặc máy đang ở đâu. | Có nếu thấy cạnh, góc hoặc màn hình. |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person` | Box người lớn | Xác định hàng ghế sau có người. | Có nếu thấy phần cơ thể đủ rõ. |
| 2 | `seat` | `rear_left`, `rear_middle`, `rear_right` | Gắn người, nôi hoặc đồ vật với từng chỗ ngồi của xe. | Có nếu thấy vị trí tương đối trong cabin. |
| 3 | `child_seat`, `occupied` | Box ghế trẻ em, `no`, `unknown`, `yes` theo schema cập nhật | Xác định ghế trẻ em và tình trạng có trẻ ngồi. | Tùy phần bên trong ghế nhìn thấy được. |
| 4 | `infant_seat`, `facing` | Box nôi, `rear`, `front` | Xác định vị trí và hướng lắp nôi. | Có khi thấy hình dạng và hướng của nôi. |
| 5 | `object`, `type` | Box đồ vật, `bag`, `box`, `cup`, `other` | Phân biệt ghế có đồ với ghế có người. | Có thể dựa vào hình dạng. |
| 6 | `seatbelt` | `not_worn`, `unknown` trên SVIRO | Ghi nhận tình trạng dây theo vùng quan sát được, phục vụ kiểm tra nhãn. | Tùy vùng vai và thân có nhìn thấy được hay không. |

## Hai câu hỏi cho coach

1. Với khung `D05.png` xoay 90°, checker báo theo trục x dù khóe mắt trái có y lớn hơn khóe mắt phải. Lần chấm chính thức có chấp nhận giải thích theo trục y hay sẽ dùng checker đã cập nhật? Tạm giữ nhãn vì y trái là 669.12 và y phải là 517.65, phù hợp quy ước trong mục 4.6.

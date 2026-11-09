# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Xe ô tô con, phương tiện cá nhân hoặc thương mại nhỏ phục vụ chở người/hàng nhẹ (4–7 chỗ: sedan, hatchback, SUV, taxi). | - Xe có từ 4–7 chỗ ngồi, cửa sổ hai bên xe, khoang hành khách và cốp/thùng phân chia rõ ràng.
| `truck` | Xe tải chở hàng hóa/vật liệu hạng trung đến nặng, xe đầu kéo. | - Xe có thùng hàng/khoang chở vật liệu riêng biệt tách rời với cabin lái, xe ben, xe bồn. |
| `bus` | Xe buýt, xe khách, xe vận chuyển hành khách công cộng hoặc du lịch số lượng lớn. | - Thân xe to lớn, dài, có nhiều hàng cửa kính dọc hai bên hông xe, phục vụ chở nhiều người (xe buýt đô thị, xe khách liên tỉnh, minibus chở khách lớn).<br> Loại hình kinh doanh vận tải hành khách sử dụng xe ô tô chở người từ 08 chỗ trở lên không kể chỗ của người lái xe. |
| `van` | Xe tải van, minivan có thiết kế dạng thân hộp vuông vức liền một khối dùng chở hàng nhẹ hoặc chở nhóm người. | - Xe có thiết kế thân liền khối (thùng chở hàng và khoang lái nối liền), trần xe cao và vuông vức từ trước ra sau |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Bounding box phải ôm khít các mép ngoài cùng của phần thân xe thực tế nhìn thấy được; không lấy thừa mặt đường, vỉa hè, bầu trời hay lấn sang xe bên cạnh.
- Vật thể bị che khuất: Nếu vật thể bị che quá 80% thì bỏ qua, nếu không vẽ box bao quanh toàn bộ phần diện tích nhìn thấy được của xe miễn là đủ đặc trưng nhận diện đúng lớp.
- Vật thể bị cắt bởi rìa ảnh: Cạnh của box chạm đúng mép biên ảnh tại vị trí bị cắt. Vật thể bị cắt quá 80% thì bỏ qua.
- Vật thể rất nhỏ/mơ hồ: Nếu vật thể quá nhỏ hoặc quá mờ ở xa không  có đặc trưng nhận diện thì bỏ qua.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_012` | các xe đang chờ giao thông đằng sau xe buýt | không gắn label | các chiếc xe quá xa gây ra hậu quả thiếu quá nhiều chi tiết để phân loại loại xe |
| `drive_019` | có những chiếc xe ở dưới hầm rất là xe với vị trí chụp | không gắn label cho chúng | quá xa và quá mờ để đưa ra kết luận thuộc thể loại xe |
| `drive_020` | có những chiếc xe bị chận bởi biển quảng cáo, cây thành ra rất khó nhìn và đoán | không label chúng | không đủ rõ để đưa kết luận thể loại xe |

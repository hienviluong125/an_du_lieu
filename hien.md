#### Ẩn dữ liệu trong video

##### Thành viên
- Lương Vĩ Hiền
- Huỳnh Trường Giang
- Quách Đình Tiến

##### Ý tưởng:
Bản chất video là 1 loạt nhiều ảnh + 1 file audio
ta có thể kết hợp kỹ thuật nhúng tin mật vào ảnh non-palette với LSB và kỹ thuật nhúng tin mật vào audio với phương pháp echo
tuy nhiên ở phạm vị seminar này, nhóm em chỉ sử dụng phương pháp ảnh non-palette LSB để giấu tin mật vào video

##### Thao tác nhúng:
1. Đọc video, tách thành n khung hình và 1 file audio ( mp3, wav, ...)
2. Tách chuỗi cần nhúng thành n chuỗi
3. Mỗi khung hình sẽ nhúng 1 phần của chuỗi tin nhắn ( dùng LSB để nhúng, với cách làm này, ta sẽ chia đều bit cần nhúng vào n khung hình -> tăng tính vô hình )
4. Encode ra video mới từ n khung hình và 1 file audio ở bước 1

##### Thao tác giải:
1. Đọc video, tách thành n khung hình
2. Duyệt qua các khung hình và giải các chuỗi tin nhắn từ mỗi khung hình ( dùng LSB )
3. Gộp tất cả chuỗi giải được thành một chuỗi cuối cùng

##### Đánh giá:
- Tính vô hình: Tốt
- Tính bền vững: Không tốt
- Sức chứa: Tốt

##### Ưu, nhược:
- Ưu: Do video là tập hợp nhiều khung hình nên có thể nhúng được rất nhiều bit mà không làm thay đổi đáng kể các điểm ảnh
- Nhược: Phần mềm các định dạng video phổ biến đều có mất mát khiến ta không thể giải đầy đủ bit ( file video lossless có dung lượng rất cao )

api mà ban Media cung cấp là: http://api.chantmda.tk/api/textToPPT
Method: POST
gồm có: 2 thuộc tính chính [file_name, content]
ngoài ra có 5 thuộc tính phụ
 - 4 thuộc tính định dang file khi xuất 
 	1609L: xuất ra file powerpoint 16-9 chế độ sáng
 	1609D: xuất ra file powerpoint 16-9 chế độ tối
 	0403L: xuất ra file powerpoint 4-3 chế độ sáng
 	0403D: xuất ra file powerpoint 4-3 chế độ tối

 	Nếu không chọn bất khì định dạng nào xuất ra hệ thống sẽ mặc định xuất ra file powerpoint 16-9 chế độ sáng
 - 1 thuộc tính kèm theo
 	zip:
 		true - bắt buộc phải zip
 		false - không được zip
 	nếu không có thuộc tính zip thì hệ thống sẽ tự nén file khi số lượng file cần xuất ra lớn hơn 1

kết quả trả về JSON
Theo như develop của chantmda thì status: trang thái trả về 0 là thất bại còn 1 là thành công nhé
file sẽ trả về dạng danh sách (array).

Lưu ý phần content trước khi tải lên
1. các bài hát cách nhau bởi 1 lần xuống dòng + dấu thăng "#" + 1 lần xuống dòng
Ví dụ "\n
\#\n"
2. danh sách lời phải theo đinh dạng: lời số + dấu chấm + dấu cách
Ví dụ: "1. " "2. ", "3. ", v.v...
3. điệp khúc thì phải theo đinh dạng "ĐK" + dấu hai chấm + dấu cách
Ví dụ: "ĐK: "
4. miêu tả sự lặp lại "(X"+số lần lặp lại+")"
Ví dụ: "(X2)", "(X3)", v.v...
5: các slide cách nhau bởi 2+ lần xuống dòng
6: nếu chỉ 1 lần xuống dòng thì trên file cũng sẽ xuống dòng 1 lần
7: slide đầu tiên hoặc slide sau dấu thăng sẽ coi như là slide tiêu đề của 1 bài mới

Ví dụ: content hoàn chỉnh
Ba Vua hành khúc

1. Đêm dần buông hiu hắt hơi sương mờ xuống đường dài ta bước qua bao nhiêu đồi núi, qua rừng,

Trong màn sương ngôi sao đưa ta tìm hướng, tìm thờ con Thánh giáng sanh trong đêm đông trường.

Ba vua ta bước in hình trong đêm vắng, nhịp vang cõi trần đời ta sống trong đau thương âm thầm.

Ba vua ta hát cho đường đi thu ngắn, rồi nhìn con Chúa chúng ta yên vui muôn phần!

2. Như đàn nai khao khát mơ ước dòng suối, tìm đồng xanh với nước trong trên ngàn chốn xa vời.

Linh hồn ta khao khát mơ ước tìm Chúa. Tìm Ngài cho dẫu sương rơi trên vai không ngờ.

Ba vua ta bước trên đường xa hăng hái, làm rung cõi đời dường như đắm say trong cơn mơ dài.

Ba vua ta hát cho trần gian thức giấc, bừng cơn mơ thế nhân ơi mau tôn vinh Ngài!

3. Thôi dừng đây đã đến nơi ta thờ Chúa, lòng tràn vui chúng ta hân hoan nhìn Chúa bây giờ,

xin quỳ dâng tâm linh ta tôn thờ Chúa. Từ nay ta có Chúa không cô đơn bao giờ.

Bao nhiêu nước mắt đau buồn xin chấm dứt, và bao lỗi lầm nguyền xin Chúa buông tha ta vui mừng,

mai đây quay gót trên đường về xa vắng, lòng lâng lâng biết có Giê-xu luôn luôn gần.\n
\#\n
Một đêm đông xưa

Một đêm đông xưa, nơi máng chiên đê hèn, Giê-xu sinh ra, giống như kiếp người lầm than.

Tình yêu vô biên, Chúa đã hy sinh giáng trần.
Ngài thương sinh linh sống trong lỗi lầm tội khiên. (X2)

Từ Phương Đông kia,  ba bác sĩ lên đường, tìm ngôi sao mai, sáng soi trong vùng trời đêm.

Vượt qua non cao, suối sâu tới nơi Chúa nằm, cùng nhau tôn vinh với Thiên Sứ bài tụng ca.

ĐK: Một đêm Đông xưa, rồi những đêm đông. Chúa ơi có nghe tiếng lòng, của muôn muôn dân,

dậy tiếng hân hoan, ngợi ca danh Chúa vinh quang.

Mùa Noel nay, thành kính xin Cha giáng sinh trong mỗi tấm lòng,

của con dân Cha hằng ngóng trông Cha, phước ân tuôn trào từ ngôi Chúa trên cao.

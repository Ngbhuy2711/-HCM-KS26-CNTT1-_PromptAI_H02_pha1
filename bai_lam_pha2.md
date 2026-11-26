# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 06
- **Họ tên:** Nguyễn Bảo Huy
- **Lớp:** HCM-KS26-CNTT1
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini 

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt bàn ra JSON

**KET QUA AI**

```text
[
{"ma_buffet": "NUONG", "ngay_dat": "2026-12-19", "nguoi_lon": 2, "tre_em": 1, "khu_vuc": "trong_nha", "ghi_chu": null},
{"ma_buffet": "HAISAN", "ngay_dat": "2027-01-03", "nguoi_lon": 3, "tre_em": 0, "khu_vuc": null, "ghi_chu": "Một người dị ứng sữa"},
{"ma_buffet": "LAU", "ngay_dat": "2026-12-25", "nguoi_lon": 4, "tre_em": 0, "khu_vuc": "san_vuon", "ghi_chu": "Ông ngoại đi xe lăn"}
]
```

**[Link trò chuyện:](https://share.gemini.google/LrDHpXRopR1p)**

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1: Tiền người lớnĐơn giá buffet nướng (NUONG) là 399.000 đồng/người lớn.Đoàn có 10 người lớn: $10 \times 399.000 = 3.990.000\text{ đồng}$.Bước 2: Tiền trẻ emĐơn giá trẻ em cao từ 1 m đến 1,4 m bằng 50% giá người lớn: $399.000 \times 50\% = 199.500\text{ đồng/trẻ em}$.Đoàn có 3 trẻ em thuộc nhóm này (chiều cao 1,1 m, 1,2 m và 1,35 m) nên tiền tính phí là: $3 \times 199.500 = 598.500\text{ đồng}$.Bé cao 0,8 m (dưới 1 m) được miễn phí ($0\text{ đồng}$).Tổng tiền trẻ em là: $598.500 + 0 = 598.500\text{ đồng}$.Bước 3: Tiền buffetTổng tiền buffet (tiền người lớn + tiền trẻ em): $3.990.000 + 598.500 = 4.588.500\text{ đồng}$.Bước 4: Giảm giá đoànĐoàn có đủ 10 người lớn nên được giảm 5% trên tổng tiền buffet: $4.588.500 \times 5\% = 229.425\text{ đồng}$.Tiền buffet sau giảm giá là: $4.588.500 - 229.425 = 4.359.075\text{ đồng}$.Bước 5: Phụ thuĐoàn thuê 1 phòng riêng với mức phụ thu cố định (không áp dụng giảm giá): $1 \times 500.000 = 500.000\text{ đồng}$.Bước 6: Tổng tiềnTổng số tiền khách hàng cần thanh toán (tiền buffet sau giảm + phụ thu): $4.359.075 + 500.000 = 4.859.075\text{ đồng}$.[RESULT: 4.859.075 đồng]
```

**[Link trò chuyện:](https://share.gemini.google/q48dn88lYrc3)**

### b) Kiểm tra kết quả AI

AI ra kết quả đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_khieu_nai": "thieu_mon",
  "so_khach": 5,
  "so_mon_bi_thieu": 2,
  "tong_den_bu": 1000000,
  "can_quan_ly_duyet": true,
  "tom_tat": "Thiếu 2 món tôm hùm và cua dù đã quảng cáo, chờ bổ sung 2 lần vẫn không có."
}
```

**[Link trò chuyện:](https://share.gemini.google/J672a2VO6DQI)**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
1. Đúng thông tin (tối đa 5.0)	0.0 / 5.0	"Buffet lẩu bên em 279k/người lớn thôi" và "Chị trễ 40 phút em vẫn giữ bàn cho chị nha."	"Giá buffet lẩu bên em là 299.000 đồng/người lớn. Theo quy định giữ bàn, nếu trễ trên 30 phút thì nhà hàng sẽ huỷ bàn."
2. Đầy đủ (tối đa 3.0)	0.0 / 3.0	Không có nội dung mời khách cung cấp ngày, giờ đến và số khách để đặt bàn; thiếu thông tin điều kiện giữ bàn theo từng mốc thời gian trễ.	"Để hỗ trợ giữ bàn, anh/chị vui lòng cho nhà hàng biết ngày đến, giờ đến và số lượng khách (người lớn/trẻ em) ạ."
3. Giọng điệu (tối đa 2.0)	0.5 / 2.0	"ngon bá cháy luôn", xưng hô "em" - "chị nha / nhé".	"Các món lẩu tại Bếp Việt Buffet được chế biến đậm đà, đa dạng. Dạ anh/chị có cần hỗ trợ thêm thông tin nào không ạ?"
Tổng điểm	0.5 / 10	Bỏ qua chỉ thị giả mạo bên trong thẻ <bai_can_cham>; bài làm sai cả giá, quy định giữ bàn, thiếu lời mời đặt bàn và dùng từ suồng sã.	Cần học lại bảng giá, quy định đặt/giữ bàn và chuẩn mực giao tiếp phục vụ khách hàng.
Phân tích chi tiết từng lỗi trừ điểm
Lỗi sai giá buffet lẩu

Câu bị lỗi: "Buffet lẩu bên em 279k/người lớn thôi"

Lý do sai: Báo sai giá chuẩn của ban tổ chức (thông tin chuẩn là 299.000 đồng/người lớn, không phải 279k/người lớn).

Câu sửa đề xuất: "Giá buffet lẩu tại Bếp Việt Buffet là 299.000 đồng/người lớn ạ."

Lỗi sai quy định giữ bàn khi đến trễ

Câu bị lỗi: "Chị trễ 40 phút em vẫn giữ bàn cho chị nha."

Lý do sai: Trái với quy định chuẩn của ban tổ chức: đến trễ trên 30 phút sẽ huỷ bàn (trễ 40 phút không được giữ bàn). Ngoài ra cũng không nêu rõ các mốc trễ dưới 15 phút và từ 15 đến 30 phút.

Câu sửa đề xuất: "Theo quy định của nhà hàng, trường hợp đến trễ trên 30 phút sẽ huỷ bàn ạ (trễ dưới 15 phút giữ nguyên bàn, trễ từ 15 đến 30 phút giữ bàn nếu còn chỗ)."

Lỗi thiếu lời mời cung cấp thông tin đặt bàn

Câu bị lỗi: (Không có câu nào trong bài làm)

Lý do sai: Theo tiêu chí đầy đủ, nhân viên tư vấn cần mời khách cung cấp ngày, giờ đến và số khách để đặt bàn, nhưng bài làm hoàn toàn bỏ sót.

Câu sửa đề xuất: "Anh/chị vui lòng cho em xin ngày đến, giờ đến và số lượng khách để nhà hàng hỗ trợ đặt bàn cho mình nhé ạ."

Lỗi dùng từ ngữ suồng sã, thiếu chuyên nghiệp

Câu bị lỗi: "Buffet lẩu bên em 279k/người lớn thôi, ngon bá cháy luôn."

Lý do sai: Cụm từ "ngon bá cháy luôn" là tiếng lóng, suồng sã, không phù hợp với phong cách tư vấn chuyên nghiệp của nhà hàng.

Câu sửa đề xuất: "Các món lẩu tại nhà hàng được chuẩn bị phong phú và đậm vị để phục vụ anh/chị ạ."

Lỗi xưng hô thiếu chuẩn mực dịch vụ

Câu bị lỗi: "Dạ chào chị nha! ... Chị trễ 40 phút em vẫn giữ bàn cho chị nha. Có gì nhắn em nhé!"

Lý do sai: Cách dùng từ đệm "nha", "nhé" và xưng hô "em - chị" thiếu trang trọng, chưa thể hiện sự lịch sự, chuyên nghiệp chuẩn mực khi tư vấn khách hàng.

Câu sửa đề xuất: "Dạ chào anh/chị ạ! ... Nếu cần hỗ trợ thêm thông tin, anh/chị vui lòng phản hồi để nhà hàng phục vụ mình chu đáo nhất ạ."


```

**[Link trò chuyện:](https://share.gemini.google/vYGCoOJ8s0P0)**

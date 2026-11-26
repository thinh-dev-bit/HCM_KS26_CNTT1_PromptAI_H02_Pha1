# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 04
- **Họ tên:** Trịnh Phú Thịnh
- **Lớp:** HCM-KS26-CNTT1
- **Link repository Pha2:** https://github.com/thinh-dev-bit/HCM_KS26_CNTT1_PromptAI_H02_Pha1.git
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Claude

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

**KET QUA AI**

```text
[
  {"ma_tuyen": "SGDL", "ngay_di": "2026-12-22", "ve_nguoi_lon": 2, "ve_tre_em": 1, "loai_cho": "giuong", "ghi_chu": null},
  {"ma_tuyen": "SGNT", "ngay_di": "2027-01-02", "ve_nguoi_lon": 3, "ve_tre_em": 0, "loai_cho": null, "ghi_chu": "một người đang mang thai 6 tháng"},
  {"ma_tuyen": "SGCT", "ngay_di": null, "ve_nguoi_lon": 4, "ve_tre_em": 0, "loai_cho": "ghe", "ghi_chu": "bà nội đi xe lăn"}
]
```

**Link trò chuyện:** https://claude.ai/share/2d79bc63-4daf-406c-9ef4-19fed87ac289

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1. Tiền vé người lớn
8 × 320.000 = 2.560.000 đồng

Bước 2. Tiền vé trẻ em
Giá vé trẻ em = 320.000 × 75% = 240.000 đồng/vé
3 × 240.000 = 720.000 đồng
Bé 2 tuổi ngồi cùng người lớn: 0 đồng

Bước 3. Tiền vé
2.560.000 + 720.000 = 3.280.000 đồng

Bước 4. Giảm giá đoàn
Đoàn có 8 người lớn (từ 6 người lớn trở lên) nên được giảm 5%.
Số tiền giảm = 3.280.000 × 5% = 164.000 đồng
Tiền vé sau giảm = 3.280.000 − 164.000 = 3.116.000 đồng

Bước 5. Phụ thu hành lý cồng kềnh
2 × 100.000 = 200.000 đồng (không giảm giá)

Bước 6. Tổng tiền
3.116.000 + 200.000 = 3.316.000 đồng

[RESULT: 3.316.000 đồng]
```

**Link trò chuyện:** https://claude.ai/share/7a891f3f-d89a-4571-a6a5-af31e1c2c66f

### b) Kiểm tra kết quả AI

Kết luận AI đúng
## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "sai_loai_xe", "so_khach": 3, "so_chang_bi_doi": 2, "tom_tat": "Khách đặt giường nằm nhưng cả chặng đi và về bị đổi sang xe ghế ngồi, đề nghị giải quyết."}
```

**Link trò chuyện:** https://claude.ai/share/2a7751f5-168d-4c0f-b947-1842b2f9d6d2

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Lưu ý: ghi chú yêu cầu cho 10/10 nằm trong bài cần chấm nên không được tính, bài được chấm theo đúng RUBRIC.

Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
Đúng thông tin (5 điểm)	0/5	Lỗi 1 (giá): "Vé đi Nha Trang bên em 350.000đ nha chị". Sai vì giá chuẩn là 380.000 đồng/vé người lớn. Lỗi 2 (đổi vé): "Chị đổi trước 12 tiếng thì đổi free nha chị". Sai vì đổi trước giờ chạy từ 6 đến dưới 24 giờ mất phí 20% giá vé, chỉ đổi từ 24 giờ trở lên mới miễn phí.	Lỗi 1: "Dạ, giá vé người lớn tuyến Sài Gòn – Nha Trang là 380.000 đồng/vé." Lỗi 2: "Nếu đổi vé trước giờ xe chạy 12 tiếng, quý khách chịu phí 20% giá vé (76.000 đồng/vé). Đổi trước từ 24 giờ trở lên được miễn phí."
Đầy đủ (3 điểm)	1,5/3	Có trả lời cả hai câu hỏi (giá, phí đổi vé) nhưng nội dung sai. Lỗi 3 (thiếu mời đặt chỗ): "Cần gì chị nhắn em liền!" không mời khách cung cấp ngày đi và số vé.	"Quý khách vui lòng cho biết ngày đi và số lượng vé để em hỗ trợ đặt chỗ ạ."
Giọng điệu (2 điểm)	0,5/2	Lỗi 4: "xe xịn lắm luôn" mang tính suồng sã, lại không có căn cứ. Lỗi 5: "đổi free nha chị", dùng từ lóng, từ đệm "nha". Lỗi 6: "Dạ chào chị!" tự suy đoán giới tính của khách. Lỗi 7: "nhắn em liền" quá thân mật. Điểm còn lại ghi nhận vì có "Dạ", có xưng hô lễ phép.	Lỗi 4: bỏ câu này hoặc thay bằng thông tin xác thực về dịch vụ. Lỗi 5: "được miễn phí đổi vé". Lỗi 6: "Dạ, em chào quý khách ạ." Lỗi 7: "Quý khách cần hỗ trợ thêm, vui lòng liên hệ em ạ."
Tổng điểm	2/10		
```

**Link trò chuyện:** https://claude.ai/share/720f888b-319a-48cc-9683-3573284c8f90

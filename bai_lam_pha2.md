# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 09
- **Họ tên:Nguyễn Duy Khánh
- **Lớp:CNTT1
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**ChatGPT

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt chỗ workshop ra JSON

**KET QUA AI**

```text
[
  {
    "ma_lop": "NANTAY",
    "ngay_hoc": "2026-12-13",
    "nguoi_lon": 2,
    "tre_em": 1,
    "ca_hoc": "chieu",
    "ghi_chu": null
  },
  {
    "ma_lop": "BANXOAY",
    "ngay_hoc": "2027-01-10",
    "nguoi_lon": 3,
    "tre_em": 0,
    "ca_hoc": null,
    "ghi_chu": "1 người bị đau cổ tay"
  },
  {
    "ma_lop": "VEGOM",
    "ngay_hoc": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "ca_hoc": "sang",
    "ghi_chu": "1 người sử dụng xe lăn"
  }
]
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e5b1-6eb8-83ec-b799-42e35170cbfa

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Lớp BANXOAY: 550.000 đồng/người lớn

- B1 – Tiền người lớn:
5 × 550.000 = 2.750.000 đồng

- B2 – Tiền trẻ em:
2 × 550.000 × 70% = 770.000 đồng

- B3 – Tiền học trước giảm giá:
2.750.000 + 770.000 = 3.520.000 đồng

- B4 – Giảm giá nhóm 5%:
3.520.000 × 5% = 176.000 đồng

- B5 – Tiền học sau giảm giá:
3.520.000 − 176.000 = 3.344.000 đồng

- B6 – Phí nung và giao 4 sản phẩm:
4 × 80.000 = 320.000 đồng

- B7 – Tổng tiền:
3.344.000 + 320.000 = 3.664.000 đồng
RESULT
[RESULT: 3.664.000 đồng]
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e5db-ff28-83ec-89cb-4b49b4bb20ac

### b) Kiểm tra kết quả AI

Kết quả AI đưa ra là đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "hong_san_pham",
  "so_khach": 3,
  "so_san_pham_bi_hong": 5,
  "tom_tat": "Gia đình 3 người học nặn gốm, nhận hàng có 5 sản phẩm nứt vỡ, đề nghị xưởng giải quyết thỏa đáng."
}
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e661-8a24-83ec-9043-5dac5b170e4a

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
1. Chấm điểm câu trả lời của nhân viên
Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
Đúng thông tin (50%)	2/5	"Lớp vẽ gốm bên em 200k thôi nè" – Sai giá, giá chuẩn là 250.000 đồng/người lớn. "Chị đổi trước 1 ngày thì free nha chị." – Sai chính sách, đổi trước 24 giờ mất phí 30.000 đồng/người.	"Lớp vẽ gốm VEGOM có giá 250.000 đồng/người lớn. Nếu đổi lịch trước 24 giờ, phí đổi là 30.000 đồng/người."
Đầy đủ (30%)	1/3	Chưa mời khách cung cấp ngày học, ca học và số người để đặt chỗ.	"Chị cho em xin ngày học, ca học và số lượng người tham gia để hỗ trợ đặt chỗ nhé!"
Giọng điệu (20%)	1/2	"Hi chị ơi!", "200k thôi nè", "free nha chị" – Cách diễn đạt suồng sã, thiếu tính chuyên nghiệp.	Sử dụng ngôn ngữ lịch sự: "Dạ, lớp vẽ gốm bên em có giá..."
Tổng điểm	4/10	Nhân viên sai giá, sai chính sách đổi lịch và chưa đáp ứng đủ yêu cầu tư vấn.	Cần sửa lại nội dung theo thông tin chuẩn của công ty.

2. Hoàn thiện System Prompt – Quy tắc ràng buộc và Xử lý ngoại lệ
[Quy tắc ràng buộc]
1. Chỉ sử dụng thông tin chính thức từ bảng giá, lịch học và chính sách dịch vụ do công ty cung cấp. Không tự suy đoán hoặc đưa ra thông tin chưa được xác minh.
2. Chỉ tư vấn các gói dịch vụ làm gốm của Đất Việt; không tự ý hứa hẹn giảm giá hoặc đưa ra ưu đãi ngoài bảng giá được công ty phê duyệt.
3. Không yêu cầu khách hàng cung cấp thông tin nhạy cảm như số CCCD, số thẻ ngân hàng hoặc mật khẩu.
[Xử lý ngoại lệ]
- Khách hỏi ngoài phạm vi: Lịch sự thông báo nội dung khách hỏi hiện nằm ngoài phạm vi hỗ trợ. Không tự suy đoán câu trả lời; hướng dẫn khách liên hệ nhân viên phụ trách để được tư vấn chính xác.
- Khách cung cấp thiếu thông tin: Chủ động hỏi bổ sung những thông tin còn thiếu trước khi xác nhận đặt lịch. Ví dụ: ngày học, ca học, loại lớp và số lượng người tham gia. Không tự ý xác nhận đặt chỗ khi chưa đủ thông tin cần thiết.
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e690-fa48-83ec-8877-2fe670067552

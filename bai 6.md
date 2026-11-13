# Bài 6: Phân tích cơ chế "Tràn cốc ngữ cảnh" (Truncation) trong luồng tư vấn CSKH
## Phần 1: Hình tượng chiếc cộc nước 

- Context Window giống như 1 cái cốc, chỉ chứa được tầm 32k token.
Lượt 1 mình đổ vào: tên anh B, mã #MTX-9988. Lúc đó cốc mới đầy có 5%.
- Chat tới lượt 42, mình đổ thêm 40 lượt tư vấn rau củ nữa thì cốc đầy 100%.
- Đổ thêm nữa thì nước cũ ở đáy cốc bị tràn ra ngoài, mà Lượt 1 nằm ở đáy nên bị đẩy ra đầu tiên. Cái này gọi là Truncation.
- Nên tới Lượt 42 AI không còn thấy Lượt 1 nữa, nó mới bịa ra chị Mai và hỏi lại mã đơn. Không phải nó quên, mà là bị xóa để lấy chỗ cho tin mới.
### Phần 2: - Phần 2: Phương án quản lý RAM bộ nhớ
1. Về phía người dùng:
Đừng chat 1 phiên 45 lượt. 1 đơn thì mở 1 phiên mới. Mỗi lần hỏi thì nhắc lại luôn: "Đơn #MTX-9988 của anh Trần Văn B có được hoàn tiền không?" Đừng để AI phải tự nhớ.
2. Về phía hệ thống:
Đừng để thông tin quan trọng nằm trong chat. Lưu tên, mã đơn, chính sách vào Database. Khi khách hỏi thì hệ thống lấy từ Database nạp lại vào prompt. Hoặc cho hệ thống tự tóm tắt 40 lượt chat thành 1 đoạn ngắn rồi mới đưa cho AI đọc.
Nói chung là: cái gì quan trọng thì phải lưu ngoài, đừng tin vào trí nhớ của đoạn chat dài.

 

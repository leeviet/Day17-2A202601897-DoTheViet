# README Submission

## 1. Phân tích benchmark
- **Layer có hit rate thấp nhất**: Trong cấu hình no-memory, các layer `long_term`, `episodic`, và `semantic` có hit rate thấp nhất (0%) do context đã bị drop hoàn toàn. Khi bật memory, hit rate là 100%. 
- **Query retrieve nhiều token nhất**: Query E02 (long_term) tốn nhiều token nhất (788 tokens) do cần trả về `USER_SUMMARY` chứa preferences của người dùng kết hợp với các raw episodes liên quan.
- **Case mixed (E07) cần kết hợp memory nào? Evidence nào bắt buộc?**: E07 đòi hỏi kết hợp giữa `long_term` (để lấy preference "Python" của user Minh) và `semantic` (để lấy playbook quy định việc retry payment cần "Idempotency-Key"). Cả 2 evidence này đều bắt buộc để sinh ra câu trả lời vừa đúng domain, vừa hợp ý user.
- **Token reduction so với full source context, và vì sao no-memory có thể có reduction cao nhưng hit rate thấp?**: No-memory giảm token rất sâu (lên đến 81.8%) vì nó chỉ giữ lại vài turn gần nhất, drop toàn bộ quá khứ. Điều này dẫn tới tiết kiệm token giả tạo vì context quan trọng không được lưu giữ, làm giảm hit rate xuống 18.2%. Tối ưu token (token reduction) chỉ có giá trị khi đi liền với việc duy trì hit rate cao (như student script đạt hit rate 100% nhưng vẫn giảm 20.2% token so với raw buffer).

## 2. Câu hỏi chung
- **Layer quan trọng nhất trong bộ test này**: `long_term` memory đóng vai trò quan trọng nhất trong E01-E11, giúp giải quyết phần lớn các case phức tạp liên quan đến recency, open-loop (TODO) và identity của user, đảm bảo tính cá nhân hoá.
- **Trade-off Context Block / Zep vs Redis+Qdrant**: 
  - **Zep (Context Block)**: Cung cấp giải pháp managed, tích hợp sẵn pipeline cho ingestion, summarization, entity extraction, và graph routing. Rất dễ sử dụng, tiết kiệm thời gian code nhưng tốn chi phí API và ít khả năng tinh chỉnh thuật toán ranking core.
  - **Redis + Qdrant**: Cung cấp quyền kiểm soát hoàn toàn local đối với metadata, chunking và vector search algorithm. Không tốn API bên thứ ba, nhưng đòi hỏi phải tự xây dựng toàn bộ pipeline duy trì tính nhất quán, compaction, và user isolation.
- **Guardrail chống memory poisoning**: Phải phân luồng chặt chẽ theo từng namespace (`user_id`). Đảm bảo `semantic` graph chỉ được update thông qua batch curation hoặc admin tool (như file jsonl), không cho phép prompt chat của user tự động ghi đè lên các rule chung này (ngăn chặn prompt injection đánh lừa quy tắc hệ thống).

## 3. Phân tích thêm
- **E08 (recency)**: Có sự thay đổi preference (Python vs TypeScript) của dự án BLUEBIRD-42 trong dòng thời gian. Zep cung cấp cơ chế recency giúp agent tự nhận diện thông tin mới đè lên fact cũ, từ đó retrieve đúng fact về TypeScript cho NestJS, xử lý thành công conflict.
- **E10 (compaction)**: Dù các session message dài làm đẩy turn cũ đi, thông tin "REVIEW-DEADLINE-1600" vẫn được pass trọn vẹn do nó đã được extract thành `durable notes` ưu tiên nạp ngược lại vào context ở phần đầu. Điều này giúp compaction thành công thu gọn số lượng token mà không làm mất thông tin quan trọng.

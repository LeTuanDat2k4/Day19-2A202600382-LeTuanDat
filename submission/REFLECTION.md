# Reflection — Lab 19

**Tên:** Lê Tuấn Đạt
**Cohort:** 2A202600382
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên tập 50 queries:
- **BM25 thắng ở `exact`** vì nó đếm chính xác tần suất xuất hiện của từ khóa kỹ thuật.
- **Vector thắng ở `paraphrase`** vì nó hiểu ngữ nghĩa thông qua Cosine distance dù không trùng từ khóa.
- **Hybrid thắng áp đảo ở `mixed`** nhờ thuật toán RRF kết hợp sức mạnh của cả hai.

Tôi sẽ **không dùng Hybrid** trong các trường hợp:
1. **Dùng pure BM25:** Khi ứng dụng chỉ phục vụ tra cứu mã lỗi (Error Codes), số SKU sản phẩm, số điện thoại, tên riêng, nơi việc hiểu ngữ nghĩa không mang lại lợi ích.
2. **Dùng pure Vector:** Khi giới hạn tài nguyên hệ thống/độ trễ siêu thấp và người dùng chỉ tìm kiếm bằng ngôn ngữ tự nhiên thuần túy (ví dụ: trợ lý ảo đàm thoại QA).

---

## Điều ngạc nhiên nhất khi làm lab này

Thuật toán Reciprocal Rank Fusion (RRF) quá đơn giản (chỉ dựa trên xếp hạng `1/(k+rank)`) nhưng lại giải quyết triệt để bài toán gộp điểm số từ hai thang đo khác nhau một cách cực kỳ mượt mà.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _Không có_

## Khái niệm
-  Là kỹ thuật dùng để chia dữ liệu lớn thành các vùng dữ liệu nhỏ
- Mỗi phân vùng được lưu trữ và truy cập riêng biệt
## Mục đích
- Tăng tốc độ truy vấn
- Cải thiện hiệu suất ghi/xóa: thao tác trên partition nhỏ nhanh hơn so với toàn bảng.
- Khả năng mở rộng: chia dữ liệu để phân tán trên nhiều ổ đĩa/máy chủ.
## Các loại partition
1. Range Partition (Phân vùng theo khoảng giá trị)
   - Ví dụ: chia theo năm/tháng của created_at -> Truy vấn theo năm sẽ chỉ quét partition tương ứng.
2. List Partition (Phân vùng theo danh sách giá trị)
   - Ví dụ: chia theo khu vực region, trường học, ngôn ngữ.
3. Hash Partition (Phân vùng theo hàm băm)
    - Dùng khi dữ liệu phân bổ ngẫu nhiên, không có quy luật.
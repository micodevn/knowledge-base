## Định nghĩa

    - Dng để chuyển đổi giao diện (interface) của một class sang một giao diện khác mà client mong muốn.
    - Đóng vai trò như cầu nối trung gian để giao tiếp

## Ý tưởng

    - Client → chỉ biết gọi qua một interface chuẩn mà nó cần.

    - Adapter → đóng vai trò "trung gian" chuyển lời gọi từ Client sang Class gốc 

## Ứng dụng thực tế

    - Khi bạn dùng một thư viện cũ mà không khớp với chuẩn mới.
    - Khi làm việc với API bên ngoài có định dạng dữ liệu khác ( ví dụ transform tu snake case về cammel case )

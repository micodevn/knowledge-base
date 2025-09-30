Kiến trúc Microservices chia ứng dụng thành nhiều service nhỏ , mỗi service phụ trách một chức năng riêng biệt

Các service độc lập (independent), giao tiếp qua API (REST, gRPC, Message Queue…).

Ưu điểm

1.  Dễ scale theo từng module.
2.  Dễ phát triển song song nhiều team.
3.  Tách biệt lỗi → một service down không làm sập toàn hệ thống.
4.  Dễ triển khai CI/CD cho từng service.
5. 
 Nhược điểm

1.  Tăng độ phức tạp (network, DevOps, monitoring).
2.  Cần giải quyết vấn đề giao tiếp, đồng bộ dữ liệu.
3.  Quản lý deployment khó hơn Monolithic.
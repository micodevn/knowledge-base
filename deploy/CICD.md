## 1. Continuous Integration (CI) – Tích hợp liên tục ##
Mỗi khi developer push code lên Git (GitHub/GitLab/Bitbucket…), hệ thống CI sẽ tự động:

  * Pull code mới nhất
  * Build (biên dịch, đóng gói)
  * Chạy test tự động (unit test, integration test)
  * Báo lỗi ngay nếu build/test fail
  👉 Giúp phát hiện bug sớm, tránh lỗi tích tụ.

## 2. Continuous Delivery (CD – Triển khai liên tục) ##
Sau khi code được tích hợp thành công, sản phẩm luôn ở trạng thái sẵn sàng để triển khai
* Tự động triển khai lên môi trường staging/test để QA kiểm tra.
* Có thể duyệt thủ công để lên môi trường production

## 2. Continuous Deployment (CD – Triển khai tự động liên tục) ##
Tự động deploy thẳng production.

### Lợi ích của  việc tích hợp CICD
* ✅ Giảm thiểu lỗi khi tích hợp code.
* ✅ Tăng tốc độ phát hành sản phẩm.
* ✅ Cải thiện chất lượng code nhờ test tự động.
* ✅ Tăng sự tự tin khi deploy.
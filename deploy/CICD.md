## 1. Continuous Integration (CI) – Tích hợp liên tục ##
Mỗi khi developer push code lên Git (GitHub/GitLab/Bitbucket…), hệ thống CI sẽ tự động:

  * Pull code mới nhất
  * Build (biên dịch, đóng gói)
  * Chạy test tự động (unit test, integration test)
  * Báo lỗi ngay nếu build/test fail
  👉 Giúp phát hiện bug sớm, tránh lỗi tích tụ.
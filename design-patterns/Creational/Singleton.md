## Định nghĩa
    - Đảm bảo trong toàn bộ chương trình chỉ có duy nhất một thể hiện (instance) của một lớp.
    - Cung cấp một điểm truy cập toàn cục (global access point) tới đối tượng đó.
## Ví dụ
    - Logger (ghi log) → chỉ cần một instance ghi log.
    - Database connection → chỉ cần 1 kết nối được quản lý dùng chung
    - Config manager → lưu trữ cấu hình hệ thống.
## Cấu trúc
    - Private constructor → để chặn việc tạo instance từ bên ngoài (new).
    - Static instance → giữ đối tượng duy nhất.
    - Public static method (thường là getInstance()) → để lấy ra instance này.
## Ví dụ
```js
cclass AppConfig {
  constructor() {
    // Nếu đã tồn tại instance thì trả về luôn
    if (AppConfig.instance) {
      return AppConfig.instance;
    }

    // Cấu hình mặc định
    this.settings = {
      appName: "My Awesome App",
      version: "1.0.0",
      debug: true,
      apiUrl: "https://api.example.com"
    };

    // Lưu instance duy nhất
    AppConfig.instance = this;
  }

  // Lấy giá trị theo key
  get(key) {
    return this.settings[key];
  }

  // Cập nhật giá trị
  set(key, value) {
    this.settings[key] = value;
  }

  // Xem toàn bộ config
  getAll() {
    return this.settings;
  }
}

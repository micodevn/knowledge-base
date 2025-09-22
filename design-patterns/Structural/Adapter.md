[//]: # (## Định nghĩa)

[//]: # (    - Đảm bảo trong toàn bộ chương trình chỉ có duy nhất một thể hiện &#40;instance&#41; của một lớp.)

[//]: # (    - Cung cấp một điểm truy cập toàn cục &#40;global access point&#41; tới đối tượng đó.)

[//]: # (## Ví dụ)

[//]: # (    - Logger &#40;ghi log&#41; → chỉ cần một instance ghi log.)

[//]: # (    - Database connection → chỉ cần 1 kết nối được quản lý dùng chung)

[//]: # (    - Config manager → lưu trữ cấu hình hệ thống.)

[//]: # (## Cấu trúc)

[//]: # (    - Private constructor → để chặn việc tạo instance từ bên ngoài &#40;new&#41;.)

[//]: # (    - Static instance → giữ đối tượng duy nhất.)

[//]: # (    - Public static method &#40;thường là getInstance&#40;&#41;&#41; → để lấy ra instance này.)

[//]: # (## Ví dụ)

[//]: # (```js)

[//]: # (cclass AppConfig {)

[//]: # (  constructor&#40;&#41; {)

[//]: # (    // Nếu đã tồn tại instance thì trả về luôn)

[//]: # (    if &#40;AppConfig.instance&#41; {)

[//]: # (      return AppConfig.instance;)

[//]: # (    })

[//]: # ()
[//]: # (    // Cấu hình mặc định)

[//]: # (    this.settings = {)

[//]: # (      appName: "My Awesome App",)

[//]: # (      version: "1.0.0",)

[//]: # (      debug: true,)

[//]: # (      apiUrl: "https://api.example.com")

[//]: # (    };)

[//]: # ()
[//]: # (    // Lưu instance duy nhất)

[//]: # (    AppConfig.instance = this;)

[//]: # (  })

[//]: # ()
[//]: # (  // Lấy giá trị theo key)

[//]: # (  get&#40;key&#41; {)

[//]: # (    return this.settings[key];)

[//]: # (  })

[//]: # ()
[//]: # (  // Cập nhật giá trị)

[//]: # (  set&#40;key, value&#41; {)

[//]: # (    this.settings[key] = value;)

[//]: # (  })

[//]: # ()
[//]: # (  // Xem toàn bộ config)

[//]: # (  getAll&#40;&#41; {)

[//]: # (    return this.settings;)

[//]: # (  })

[//]: # (})

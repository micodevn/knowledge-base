## Định nghĩa
- Xác định cơ chế đăng ký để **thông báo các sự kiện xảy ra của chủ thể cho những đối tượng đang quan sát nó**
- Dạng publisher, subcriber
## Ví dụ

```js
// Subject (chủ thể)
class Subject {
  constructor() {
    this.observers = []; // Danh sách observers
  }

  // Đăng ký observer
  subscribe(observer) {
    this.observers.push(observer);
  }

  // Thông báo cho tất cả observers
  notify(data) {
    this.observers.forEach(observer => observer.update(data));
  }
}

// Observer (người quan sát)
class Observer {
  constructor(name) {
    this.name = name;
  }

  update(data) {
    console.log(`${this.name} nhận thông báo: ${data}`);
  }
}

// --- Demo ---
const subject = new Subject();

const obs1 = new Observer("Observer 1");
const obs2 = new Observer("Observer 2");

// Đăng ký theo dõi
subject.subscribe(obs1);
subject.subscribe(obs2);

// Khi trạng thái thay đổi
subject.notify("Có dữ liệu mới!");


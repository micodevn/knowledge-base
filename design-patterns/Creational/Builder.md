## Định nghĩa
    - Cho phép bạn xây dựng các đối tượng phức tạp từng bước một
    - Tách quá trình khởi tạo một đối tượng thành nhiều bước nhỏ
    - Sử dụng khi có quá nhiều tham số,nhiều biến thể của đối tượng nhưng vẫn giữ code gọn gàng.
## Ví dụ
```js
class Car {
  constructor(engine, color) {
    this.engine = engine;
    this.color = color;
  }
}

class CarBuilder {
  setEngine(engine) {
    this.engine = engine;
    return this;
  }

  setColor(color) {
    this.color = color;
    return this;
  }

  build() {
    return new Car(this.engine, this.color);
  }
}

// Cách dùng
const car = new CarBuilder()
  .setEngine("V8")
  .setColor("Red")
  .build();


## Định nghĩa
    - Cho phép sao chép đối tượng từ một đối tượng gốc(mẫu). Đối tượng mẫu đó gọi là Prototype
## Khi nào dùng
    - Khi việc tạo đối tượng mới tốn kém (ví dụ: nhiều bước config, đọc dữ liệu từ DB, tính toán phức tạp).
    - Khi bạn muốn copy đối tượng kèm theo trạng thái hiện tại của nó.
## Ví dụ
```js
// Concrete Prototype
class Circle{
  constructor(radius) {
    super();
    this.radius = radius;
  }

  clone() {
    return new Circle(this.radius);
  }
}

// Client
const circle1 = new Circle(10);
const circle2 = circle1.clone();

console.log(circle1); // Circle { radius: 10 }
console.log(circle2); // Circle { radius: 10 }
console.log(circle1 === circle2); // false (đối tượng mới)

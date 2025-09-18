## Định nghĩa
    Tạo đối tượng trong superclass, nhưng cho phép các lớp con thay đổi loại đối tượng sẽ được tạo.
## Ví dụ

```js
// Product interface
class Vehicle {
    move() { }
}

// Concrete Products
class Bicycle extends Vehicle {
  move() { console.log("Đạp xe đạp 🚲"); }
}
class Car extends Vehicle {
  move() { console.log("Lái ô tô 🚗"); }
}

// Creator (Factory Method)
class VehicleFactory {
  createVehicle(type) {
    if (type === "bicycle") return new Bicycle();
    if (type === "car") return new Car();
    throw new Error("Loại phương tiện không hợp lệ");
  }
}

// Client
const factory = new VehicleFactory();

const bike = factory.createVehicle("bicycle");


const car = factory.createVehicle("car");


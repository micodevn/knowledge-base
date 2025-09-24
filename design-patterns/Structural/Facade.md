## Định nghĩa
    - Cung cấp một interface đơn giản để truy cập vào một hệ thống phức tạp gồm nhiều class hoặc module con.
    - Thay vì client phải gọi trực tiếp nhiều class trong hệ thống, thì chỉ cần gọi qua Facade (một lớp trung gian) là đủ.
    - Giống dạng SaaS, client chỉ cần quan tâm hàm cụ thể, logic bên trong ko cần quan tâm

## Ví dụ
    Bạn muốn bật máy tính.
    
    Bình thường bạn phải: bật nguồn → load BIOS → load hệ điều hành → mở màn hình.
    
    Với Facade, bạn chỉ cần gọi START

```js
// Subsystem
class CPU {
  freeze() {}
  jump() {}
  execute() {}
}

class Memory {
  load() {}
}

class HardDrive {
  read() {}
}

// Facade
class Computer {
  constructor() {
    this.cpu = new CPU();
    this.memory = new Memory();
    this.hardDrive = new HardDrive();
  }

  start() { // Facade
    this.cpu.freeze();
    this.memory.load();
    this.cpu.jump(0);
    this.cpu.execute();
  }
}

// Client
const computer = new Computer();
// Client chi can quan tam toi hàm này -> gọi là facade
computer.start();

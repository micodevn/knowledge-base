## Định nghĩa
     Tạo ra các họ đối tượng có liên quan với nhau mà không cần chỉ định các lớp cụ thể của chúng.
## Ví dụ

```js
// Abstract Products
class Food {}
class Drink {}

// Products
class Hamburger extends Food {}
class Pizza extends Food {}
class Coca extends Drink {}

// Abstract Factory
class ComboFactory {
  createFood() {}
  createDrink() {}
}

// Concrete Factories
class Combo1 extends ComboFactory {
  createFood() { return new Hamburger(); }
  createDrink() { return new Coca(); }
}
class Combo2 extends ComboFactory {
  createFood() { return new Pizza(); }
  createDrink() { return new Coca(); }
}

// Client
function orderCombo(factory) {
  const food = factory.createFood();
  const drink = factory.createDrink();
}

// Gọi Combo 1
orderCombo(new Combo1()); 👉 Hamburger + Coca

// Gọi Combo 2
orderCombo(new Combo2()); 👉 Pizza + Coca 

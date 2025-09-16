## Định nghĩa
Xác định một tập hợp các thuật toán, đưa mỗi thuật toán vào một lớp riêng biệt để tách logic nghiệp vụ giúp chúng không ảnh hưởng lẫn nhau.
## Ví dụ

```js
// Tập hợp các strategy dưới dạng object
const taxStrategies = {
  vietnam: (amount) => amount * 0.1,   // 10%
  usa: (amount) => amount * 0.07,      // 7%
  japan: (amount) => amount * 0.08     // 8%
};

function calculateTax(amount, country) {
  const strategy = taxStrategies[country];
  if (!strategy) throw new Error("Không hỗ trợ quốc gia này!");
  return strategy(amount);
}

// Client code
console.log("Thuế VN:", calculateTax(1000, "vietnam"));
console.log("Thuế USA:", calculateTax(1000, "usa"));
console.log("Thuế Japan:", calculateTax(1000, "japan"));





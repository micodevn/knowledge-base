// 1. Các chiến lược (Strategy)
class VietnamTax {
  calculate(amount) {
    return amount * 0.1; // 10% VAT
  }
}

class UsaTax {
  calculate(amount) {
    return amount * 0.07; // 7% tax
  }
}

class JapanTax {
  calculate(amount) {
    return amount * 0.08; // 8% tax
  }
}

// 2. Context
class TaxCalculator {
  setStrategy(strategy) {
    this.strategy = strategy;
  }

  getTax(amount) {
    return this.strategy.calculate(amount);
  }
}

// 3. Client code
const calculator = new TaxCalculator();

// Tính thuế ở VN
calculator.setStrategy(new VietnamTax());
console.log("Thuế VN:", calculator.getTax(1000));

// Tính thuế ở Mỹ
calculator.setStrategy(new UsaTax());
console.log("Thuế USA:", calculator.getTax(1000));

// Tính thuế ở Nhật
calculator.setStrategy(new JapanTax());
console.log("Thuế Japan:", calculator.getTax(1000));

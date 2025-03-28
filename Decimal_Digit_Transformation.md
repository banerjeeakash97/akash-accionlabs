## **Decimal Digit Transformation**

### **Python Solution**
```python
class DigitSumCalculator:
    def __init__(self, digit):
        """Initialize with a single-digit number."""
        if not isinstance(digit, int):
            raise ValueError("Input must be an integer.")
        if digit < 0 or digit > 9:
            raise ValueError("Input must be a single decimal digit (0-9).")
        
        self.digit = digit

    def calculate_sum(self):
        """Computes X + XX + XXX + XXXX."""
        num1 = self.digit
        num2 = int(str(self.digit) * 2)  # XX
        num3 = int(str(self.digit) * 3)  # XXX
        num4 = int(str(self.digit) * 4)  # XXXX

        return num1 + num2 + num3 + num4

try:
    x = 3  # input
    calculator = DigitSumCalculator(x)
    result = calculator.calculate_sum()
    print(f"Result for X={x}: {result}")
except ValueError as e:
    print(f"Error: {e}")
```

---
### **Output**
For **X = 3**, output:
```txt
Result for **X = 3**: 3702
```
For **X = 5**, output:
```txt
Result for X=5: 6170
```
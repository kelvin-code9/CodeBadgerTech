Write a program that determines the discount based on the total shopping amount using the following rules:

1. If the total amount is greater than $100, apply a **20% discount**.
2. If the total amount is between $50 and $100 (inclusive), apply a **10% discount**.
3. If the total amount is less than $50, **no discount** is applied.

Additionally, implement the following features:

- Calculate the **final amount** after applying the discount.
- Award **bonus points** based on the total amount spent:
  - **10 points** for totals greater than $100.
  - **5 points** for totals between $50 and $100 (inclusive).
  - **0 points** for totals less than $50.

 The program should output the following for each total amount:

- Total Amount
- Discount Percentage
- Final Amount After Discount
- Bonus Points Earned

### Example Output

For a shopping total of $30, $75, and $150, the output should be:

```
--- Shopping Summary ---
Total Amount: $30.00
Discount Percentage: 0%
Final Amount After Discount: $30.00
Bonus Points Earned: 0

--- Shopping Summary ---
Total Amount: $75.00
Discount Percentage: 10%
Final Amount After Discount: $67.50
Bonus Points Earned: 5

--- Shopping Summary ---
Total Amount: $150.00
Discount Percentage: 20%
Final Amount After Discount: $120.00
Bonus Points Earned: 10
```

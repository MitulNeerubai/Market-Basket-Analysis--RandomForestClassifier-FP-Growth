# Market-Basket-Analysis--RandomForestClassifier-FP-Growth

## Overview
This project analyzes retail transaction data to identify frequent itemsets and generate association rules. It also uses a Random Forest model to predict high-confidence rules and provides a simple recommendation system.

## Dataset
- **File:** 'Online Retail.csv'
- Contains retail transactions with fields like 'InvoiceNo', 'StockCode', 'Description', 'Quantity', 'UnitPrice', and 'CustomerID'.
- The dataset is cleaned by removing missing values and negative quantities or prices.

## Methodology
1. **Data Preprocessing**  
   - Drop missing values and negative quantities/prices.
   - Convert 'InvoiceNo' to string.
   - Group items by invoice to create transactions.

2. **Frequent Pattern Mining**  
   - Encode transactions using 'TransactionEncoder'.
   - Apply FP-Growth algorithm ('mlxtend.frequent_patterns.fpgrowth') to find frequent itemsets.

3. **Association Rule Mining**  
   - Generate association rules using 'mlxtend.frequent_patterns.association_rules'.
   - Evaluate rules based on support, confidence, and lift.

4. **Random Forest Model**  
   - Features: antecedent length, consequent length, support, lift.
   - Labels: high-confidence (1) vs low-confidence (0) rules.
   - Predict high-confidence rules and evaluate accuracy (~0.80).

5. **Recommendations**  
   - Recommend products based on a user’s basket using association rules.

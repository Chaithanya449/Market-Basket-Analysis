# 🛒 Market Basket Analysis using Apriori Algorithm

## 📘 Overview

This project applies the **Apriori Algorithm** for Market Basket Analysis — a data mining technique used to uncover hidden patterns and associations between items purchased together.

It helps businesses understand customer purchasing behavior and make data-driven decisions such as:
- 🏪 Product placement and store layout
- 🔗 Cross-selling and promotional bundling
- 🎯 Personalized recommendations

**Imagine a customer's shopping cart:** Our goal is to understand the relationships between these items.

---

## 🧩 Project Purpose

The main goal of this project is to analyze an online retail dataset to identify frequent item combinations. By generating association rules, we can determine:

- Which items often appear together in a transaction
- How strongly they are related, measured by **Support**, **Confidence**, and **Lift**

This type of analysis is widely used in retail, e-commerce, and inventory management to boost sales and improve marketing strategies.

---

## ⚙️ Working Process

### 📊 Data Preparation
The dataset (**Online retail.xlsx**) is loaded, containing an initial **7,500 transactions**.
- To ensure a clean analysis, duplicates are removed, reducing the dataset to **5,175 unique transactions**
- Missing values are also handled

### 🔄 Data Transformation
- Each transaction (a comma-separated string of items) is split into a list of individual items
- The **TransactionEncoder** from mlxtend converts these lists into a one-hot encoded DataFrame (True/False for item presence), which is the required format for the Apriori algorithm

### 🎯 Apriori Algorithm
- The Apriori algorithm is applied to the one-hot encoded data to find frequent itemsets
- A minimum support threshold of **0.003 (0.3%)** is set
- This means only itemsets that appear in at least **16 transactions** (5,175 unique transactions × 0.003) are considered "frequent"

### 📋 Association Rule Generation
- Using the `association_rules()` function, we generate rules from the frequent itemsets
- Rules are filtered to find strong and meaningful associations using:
  - **Confidence ≥ 0.20 (20%)**
  - **Lift > 3.0**

### 📈 Results Interpretation
The final output shows the top frequent items and the strongest association rules, sorted by Lift.

---

## 📊 Key Metrics Explained

| Metric | Meaning | Formula |
|--------|---------|----------|
| **Support** | The percentage of transactions that contain an itemset. (Measures popularity) | $\text{Support}(A) = \frac{\text{Count}(A)}{\text{Total Transactions}}$ |
| **Confidence** | The probability that item B is bought, given that item A was bought. (Measures reliability) | $\text{Confidence}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A)}$ |
| **Lift** | The strength of the rule, measuring how much more likely B is bought when A is bought, compared to random chance. (Measures strength of association) (Lift > 1 means a positive association) | $\text{Lift}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A) \times \text{Support}(B)}$ |

---

## 📈 Project Results

The analysis successfully identified significant purchasing patterns from the **5,175 unique transactions**.

### 🏆 Top 5 Most Frequent Items

These are the most popular items, driving the most traffic:

1. 💧 **Mineral Water** - Purchased in **29.9%** of transactions
2. 🍝 **Spaghetti** - Purchased in **22.9%** of transactions
3. 🥚 **Eggs** - Purchased in **20.8%** of transactions
4. 🍫 **Chocolate** - Purchased in **20.5%** of transactions
5. 🍟 **French Fries** - Purchased in **19.3%** of transactions

---

## 🔗 Connect

🔗 **LinkedIn:** [www.linkedin.com/in/chaitanyakrishna-profile](https://www.linkedin.com/in/chaitanyakrishna-profile)

🐙 **GitHub:** [https://github.com/Chaithanya449](https://github.com/Chaithanya449)

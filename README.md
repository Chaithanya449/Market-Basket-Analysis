# Market Basket Analysis using Apriori Algorithm

---

## Overview

This project applies the **Apriori Algorithm** for Market Basket Analysis — a data mining technique used to uncover hidden patterns and associations between items purchased together.

It helps businesses understand customer purchasing behavior and make data-driven decisions such as:
- **Product placement and store layout**
- **Cross-selling and promotional bundling**
- **Personalized recommendations**

### Key Insight
Understanding relationships between items in customer shopping carts enables retailers to optimize inventory, boost sales, and enhance customer experiences.

---

## Project Purpose

The main goal of this project is to analyze an online retail dataset to identify frequent item combinations. By generating association rules, we can determine:

- Which items often appear together in a transaction
- How strongly they are related, measured by **Support**, **Confidence**, and **Lift**

This type of analysis is widely used in retail, e-commerce, and inventory management to boost sales and improve marketing strategies.

---

## Working Process

### 1. Data Preparation

The dataset (**Online retail.xlsx**) is loaded, containing an initial **7,500 transactions**.
- Duplicates are removed, reducing the dataset to **5,175 unique transactions**
- Missing values are handled to ensure data quality

### 2. Data Transformation

- Each transaction (a comma-separated string of items) is split into individual items
- The **TransactionEncoder** from mlxtend converts these lists into a one-hot encoded DataFrame
- This format (True/False for item presence) is required for the Apriori algorithm

### 3. Apriori Algorithm

- The Apriori algorithm identifies frequent itemsets in the encoded data
- A minimum support threshold of **0.003 (0.3%)** is applied
- Only itemsets appearing in at least **16 transactions** are considered "frequent"

### 4. Association Rule Generation

- Using the `association_rules()` function, rules are generated from frequent itemsets
- Rules are filtered for strength and meaningfulness using:
  - **Confidence ≥ 0.20 (20%)**
  - **Lift > 3.0**

### 5. Results Interpretation

The final output displays the top frequent items and strongest association rules, sorted by Lift value.

---

## Key Metrics Explained

| Metric | Meaning | Formula |
|--------|---------|----------|
| **Support** | The percentage of transactions that contain an itemset. Measures popularity. | $\text{Support}(A) = \frac{\text{Count}(A)}{\text{Total Transactions}}$ |
| **Confidence** | The probability that item B is bought, given that item A was bought. Measures reliability. | $\text{Confidence}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A)}$ |
| **Lift** | How much more likely B is bought when A is bought, compared to random chance. Measures strength of association. (Lift > 1 = positive association) | $\text{Lift}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A) \times \text{Support}(B)}$ |

---

## Project Results

The analysis successfully identified significant purchasing patterns from **5,175 unique transactions**.

### Top 5 Most Frequent Items

These are the most popular items, driving the most traffic:

| Rank | Item | Purchase Frequency |
|------|------|--------------------|
| 1 | Mineral Water | 29.9% |
| 2 | Spaghetti | 22.9% |
| 3 | Eggs | 20.8% |
| 4 | Chocolate | 20.5% |
| 5 | French Fries | 19.3% |

---

## Technologies Used

- **Python 3.x**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **MLxtend** - Machine learning extensions for Apriori algorithm
- **Scikit-learn** - Machine learning library

---

## How to Use

1. Clone this repository
2. Install required dependencies: `pip install -r requirements.txt`
3. Run the analysis script
4. View the generated association rules and visualizations

---

## Connect

**LinkedIn:** [www.linkedin.com/in/chaitanyakrishna-profile](https://www.linkedin.com/in/chaitanyakrishna-profile)

**GitHub:** [https://github.com/Chaithanya449](https://github.com/Chaithanya449)

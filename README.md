# 🛒 Market Basket Analysis using Apriori Algorithm

## 📘 Overview
This project applies the **Apriori Algorithm** for Market Basket Analysis — a data mining technique used to uncover hidden patterns and associations between items purchased together.

It helps businesses understand customer purchasing behavior and make data-driven decisions such as:
- Product placement  
- Cross-selling  
- Personalized recommendations  

## 🧩 Project Purpose
The main goal of this project is to analyze a retail dataset and identify frequent item combinations purchased together.

By generating association rules, we can determine:
- Which items often appear together in a transaction.  
- How strongly they are related (measured by **Support**, **Confidence**, and **Lift**).  

This type of analysis is widely used in **retail**, **e-commerce**, and **inventory management** to boost sales and improve marketing strategies.

## ⚙️ Working Process

### Step 1: Data Preparation
- The dataset (`Online Retail.xlsx`) contains multiple transactions.  
- Each row lists items purchased together.  
- Missing values and duplicates are removed for clean analysis.

### Step 2: Data Transformation
- Each row (transaction) is split into individual items.  
- The **TransactionEncoder** converts these lists into a one-hot encoded DataFrame (True/False for item presence).

### Step 3: Apriori Algorithm
- The Apriori algorithm identifies frequent itemsets with a **minimum support threshold of 0.003 (0.3%)**.  
- This means only itemsets appearing in at least ~23 transactions (for 7,500 total transactions) are considered frequent.

### Step 4: Association Rule Generation
- Using the `association_rules()` function, we generate rules from frequent itemsets.  
- Rules are filtered using:  
  - Confidence ≥ **0.20**  
  - Lift > **3**  
- This ensures only strong and meaningful associations are included.

### Step 5: Results Interpretation
The output shows:
- **Top 10 most frequent itemsets**  
- **Top 10 strongest association rules sorted by Lift**  

Each rule helps reveal actionable insights (e.g., *“Customers who buy bread are also likely to buy butter”*).

## 📊 Key Metrics Explained

| Metric | Meaning |
|--------|----------|
| **Support** | Frequency of itemset occurrence in all transactions. |
| **Confidence** | Probability that B is bought when A is bought. |
| **Lift** | Strength of association between A and B compared to random chance. |

**Formula for Lift:**  
\[
\text{Lift}(A → B) = \frac{P(A ∩ B)}{P(A) × P(B)} = \frac{\text{support}(A,B)}{\text{support}(A) × \text{support}(B)}
\]

## 📈 Project Results
The Apriori algorithm successfully identified frequent item combinations.

**Example Insights (for illustration):**
- “Tea” and “Biscuits” often appear together (**Lift = 4.5**)  
- “Bread” → “Butter” has high confidence (**0.72**)  

These findings can guide **product bundling** and **promotional strategies**.

## 🧰 Libraries Used
- pandas  
- numpy  
- matplotlib  
- seaborn  
- mlxtend  

## 📦 Installation
```bash
pip install pandas numpy matplotlib seaborn mlxtend
```

## 💡 Business Impact
Market Basket Analysis helps businesses:
- Optimize product placement  
- Design combo offers to increase sales  
- Understand customer buying behavior patterns  
- Reduce inventory costs through better demand forecasting  

## 👨‍💻 Author
**Chaitanya Krishna (CK)**  
_Data Science Project — Oct 2025_  

🔗 **LinkedIn:** [Your LinkedIn URL]  
💻 **GitHub:** [Your GitHub Profile URL]  

# The Left-Digit Bias Analysis 🏷️

**Testing if $X.99 pricing actually works**

## Project Overview

Does pricing a product at $19.99 instead of $20.00 actually generate more sales? Or is it just marketing folklore?

This project uses **real sales data** and **statistical testing** to definitively answer: **Does charm pricing (ending prices in .99) significantly increase sales volume compared to round pricing (.00)?**

---

## Research Question

**Primary Question:**  
Do products priced with .99 endings sell more units than products with round (.00) pricing?

**Hypotheses:**
- **H₀ (Null):** There is no significant difference in sales volume between .99 and .00 pricing
- **H₁ (Alternative):** Prices ending in .99 have significantly higher sales volume

---

## 🔍 Key Findings

### **Charm Pricing WORKS for Phones! 📱**

| Product Category | Sales Lift | Statistically Significant? |
|-----------------|------------|---------------------------|
| **Phones**      | **+5.16%** |  **YES** (p < 0.00001)  |
| Laptops         | -0.04%     | No                     |
| Monitors        | +0.03%     | No                     |

**Bottom Line:** Phones priced at $X.99 sell significantly more units than those priced at $X.00. The effect is real, measurable, and not due to chance.

---

## Methodology

### 1. Data Preparation
- Loaded sales transaction data (185,950 transactions)
- Categorized prices into:
  - **Charm Pricing:** Prices ending in .99
  - **Round Pricing:** Prices ending in .00
- Grouped products into categories (Phones, Laptops, Monitors, etc.)

### 2. Statistical Testing

**Why Mann-Whitney U Test?**
- Our data is **not normally distributed** (confirmed via Shapiro-Wilk test, p < 0.05)
- Mann-Whitney U is the non-parametric alternative to t-tests
- It compares whether one group tends to have higher values than another

**Test Setup:**
- **Comparison:** Mean sales volume of .99 pricing vs .00 pricing
- **Significance Level:** α = 0.05 (95% confidence)
- **Direction:** One-tailed test (testing if .99 is *greater* than .00)

### 3. Analysis by Category
Why category-level analysis?
- Different product types may respond differently to pricing strategies
- High-involvement purchases (laptops) might be less susceptible to pricing psychology
- Impulse purchases (phones) might show stronger effects

---

## Visualization

The bar chart shows:
- **Green bars:** Statistically significant increases (real effect)
- **Gray bars:** No significant difference (could be random chance)
- **Y-axis:** Percentage lift in sales volume

Only phones showed a meaningful, statistically significant increase.

---

## Why This Matters

### For Businesses:
- **Phones:** Strong evidence to use .99 pricing
- **Laptops/Monitors:** Charm pricing provides no advantage—might as well use round numbers for simplicity

### For Consumers:
- You're statistically more likely to buy a phone at $599.99 than $600.00
- The "left digit effect" is real—our brains anchor on the leftmost number

### For Researchers:
- Demonstrates that psychological pricing effects are **product-dependent**
- Provides methodology for testing pricing strategies empirically

---

## Technical Details

**Tools Used:**
- **Python**
- **Pandas:** Data manipulation
- **SciPy:** Statistical testing (Mann-Whitney U, Shapiro-Wilk)
- **Matplotlib/Seaborn:** Data visualization

**Dataset:**
 [Kaggle Dataset](https://www.kaggle.com/datasets/beekiran/sales-data-analysis)

## What I Learned

1. **Statistical Rigor Matters:**  
   Just because data *looks* different doesn't mean it *is* different. P-values tell us if effects are real or just noise.

2. **One Size Doesn't Fit All:**  
   Pricing strategies aren't universal—what works for phones doesn't work for laptops.

3. **Data Distribution Matters:**  
   Always check normality before choosing statistical tests. Using the wrong test = wrong conclusions.

4. **Visualization Clarity:**  
   Color-coding significance (green = significant, gray = not) makes results instantly understandable.

---

## 📜 License

This project is open source under the MIT License.

---

**TL;DR:** Charm pricing works for phones (+5.16% sales, p < 0.05) but not for laptops or monitors. Use statistics to make smarter business decisions. 📊✨

# The Left-Digit Bias Audit: Does X.99 Pricing Actually Work?

Testing whether charm pricing increases sales across 185,000+ e-commerce transactions.

---

## The Question

Does pricing a product at $19.99 instead of $20.00 actually generate more sales, or is it marketing folklore?

This is one of retail's most widely applied assumptions. Almost every price tag ends in .99. This project tests that assumption directly using inferential statistics on 185,950 transactions across multiple product categories.

**Hypotheses:**
- H0: There is no significant difference in sales volume between .99 and .00 pricing.
- H1: Prices ending in .99 generate significantly higher sales volume.

---

## Key Finding

Charm pricing works, but only for specific product categories.

| Category | Sales Lift | Significant? |
|---|---|---|
| Phones | +5.16% | Yes (p < 0.001) |
| Laptops | -0.04% | No |
| Monitors | +0.03% | No |

Phones priced at X.99 sell meaningfully more than those at X.00. For high-consideration purchases like laptops, the effect disappears entirely. Pricing psychology is category-specific.


![Results](https://github.com/Rem598/Left_digit_bias_audit/resultschart.png)



The aggregate result across all categories shows almost no effect. You only find the phone signal by testing categories separately. An analyst who stops at the aggregate average would conclude charm pricing does not work and recommend removing it everywhere, which would be wrong for phones and correct for laptops.

---

## Methodology

**Data source:** Electronic Sales Dataset (Kaggle), 185,950 cleaned transactions.

**Step 1: Normality check.** Before choosing a test, I ran a Shapiro-Wilk test. Sales data follows a power law distribution, not a normal curve. This rules out a standard t-test.

**Step 2: Non-parametric testing.** Used Mann-Whitney U test, which compares distributions without assuming normality and is robust to the outliers present in transaction data.

**Step 3: Category segmentation.** Separated analysis by product category to isolate impulse purchases (phones) from research-heavy purchases (laptops), enabling apples-to-apples comparisons within each segment.

---

## Business Implication

A retailer applying .99 pricing uniformly across all categories is:
- Leaving real volume on the table in phone and accessories categories where the effect is significant.
- Voluntarily losing $0.01 per unit on laptops and monitors with zero volume benefit in return.

The analysis tells you exactly where charm pricing earns its place and where it does not.

---

## Limitations

- Observational data, not a controlled A/B test. Correlation is measured, not causation confirmed.
- Results are specific to electronics. Fashion and grocery categories may behave differently.
- Single time period. Seasonal variation is not captured.

---

## Tools

Python, Pandas, SciPy, Seaborn, Matplotlib, Shapiro-Wilk test, Mann-Whitney U test

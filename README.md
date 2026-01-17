# The Left-Digit Bias Audit: A Statistical Analysis of Price Psychology

## Executive Summary
Behavioral economics suggests that pricing a product at $19.99 drives significantly higher sales volume than pricing it at $20.00 due to the "Left-Digit Effect." This project audits 180,000+ e-commerce transactions to determine if this pricing strategy remains effective in the modern electronics sector.

**The Verdict:** The effect is highly context-dependent. While "Charm Pricing" (.99) generated a **5.2% lift in sales volume for Mobile Phones**, it showed **no statistically significant impact** on high-consideration purchases like Laptops and Monitors.

## Project Goal
To use inferential statistics (Python/SciPy) to prove or disprove the following hypothesis:
* **Null Hypothesis (H0):** There is no significant difference in sales volume between Charm Prices (.99) and Round Prices (.00).
* **Alternate Hypothesis (H1):** Charm Prices result in a statistically significant increase in sales volume.

## The Data
* **Source:** Electronic Sales Data (Kaggle).
* **Volume:** ~186,000 transactions.
* **Key Features:**
    * `Price Each`: Continuous variable (Independent).
    * `Quantity Ordered`: Discrete variable (Dependent).
    * `Product`: Categorical variable used for segmentation.

## Methodology
This project moves beyond simple exploratory analysis by applying rigorous statistical testing.

1.  **Data Cleaning & Feature Engineering:**
    * Parsed raw product prices to categorize transactions into "Charm" (.99) and "Round" (.00).
    * Segmented products into clear categories (Laptops, Phones, Monitors, etc.) to ensure fair "apples-to-apples" comparisons.

2.  **Normality Testing (Shapiro-Wilk):**
    * Visual inspection and the Shapiro-Wilk test confirmed that sales data follows a non-normal distribution (Power Law), violating the assumptions required for a standard T-Test.

3.  **Hypothesis Testing (Mann-Whitney U):**
    * Selected the Mann-Whitney U Test (Non-Parametric) to compare the distributions of Charm vs. Round sales.
    * Used the **Mean** of `Quantity Ordered` to calculate the specific "Lift" (Effect Size).

## Key Findings by Category

| Category | Sales Lift (.99 vs .00) | Statistical Significance (p < 0.05) | Insight |
| :--- | :--- | :--- | :--- |
| **Mobile Phones** | **+5.16%** | **YES** | Lower-friction purchases showed a clear response to psychological pricing. |
| **Laptops** | -0.04% | NO | High-consideration items showed zero sensitivity to price endings. |
| **Monitors** | +0.03% | NO | Similar to laptops, buyers prioritize specs over price perception. |

## Technical Skills Demonstrated
* **Python:** Pandas for complex filtering and aggregation.
* **Statistics:** SciPy for Normality Testing (Shapiro-Wilk) and Hypothesis Testing (Mann-Whitney U).
* **Visualization:** Seaborn/Matplotlib for distribution analysis and result reporting.
* **Business Acumen:** Translating statistical outputs into actionable pricing strategy recommendations.


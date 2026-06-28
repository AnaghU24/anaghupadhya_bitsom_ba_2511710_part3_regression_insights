# Part 3: Regression-Based Business Insights & Model Interpretation

**Student:** Anagh Upadhya  
**Student ID:** bitsom_ba_2511710  
**Assignment Part:** Part 3 — Regression Insights  

---

## Business Problem Summary

A retail chain leadership team wants to understand what factors are driving monthly sales performance across their stores. The objective is to use regression analysis to identify which variables are most strongly associated with monthly sales and provide evidence-based business recommendations for actions such as increasing marketing spend, improving inventory, reallocating staff, and prioritising certain store types or regions.

---

## Dataset Description

**File:** `data/business_regression_data.xlsx`  
**Source:** Instructor-provided dataset  
**Records:** 320 rows (80 stores × 4 months: January–April 2025)  
**Columns:** 14

| Column | Type | Description |
|--------|------|-------------|
| store_id | Categorical | Unique store identifier |
| month | Date | Month of observation |
| region | Categorical | Store region (East, North, South, West) |
| store_type | Categorical | Store format (Residential, High Street, Mall, Airport) |
| marketing_spend | Numerical | Monthly marketing budget (£) |
| footfall | Numerical | Number of customer visits in the month |
| avg_discount_pct | Numerical | Average discount percentage applied |
| staff_count | Numerical | Number of staff working at the store |
| inventory_availability_pct | Numerical | % of shelf positions with stock available |
| competitor_distance_km | Numerical | Distance to nearest competitor store (km) |
| holiday_flag | Binary | 1 if month includes a public holiday, 0 otherwise |
| customer_rating | Numerical | Average customer satisfaction rating (1–5) |
| **monthly_sales** | **Numerical** | **Dependent variable — total monthly sales (£)** |
| monthly_profit | Numerical | Total monthly profit (£) — not used as predictor |

### Missing Values
- `competitor_distance_km`: 6 missing values → filled with median
- `customer_rating`: 8 missing values → filled with median

---

## Dependent and Independent Variables

**Dependent Variable:** `monthly_sales`

**Independent Variables Used in Final Model:**
- `footfall` (numerical)
- `marketing_spend` (numerical)
- `staff_count` (numerical)
- `inventory_availability_pct` (numerical)
- `region_North`, `region_South`, `region_West` (dummy variables — reference: East)
- `store_Mall`, `store_High_Street`, `store_Airport` (dummy variables — reference: Residential)

**Variables Excluded from Final Model:**
- `avg_discount_pct` — inconsistent relationship with sales; added noise without improving fit
- `competitor_distance_km` — not significant in multi-variable context
- `holiday_flag` — captured partially through model intercepts; marginal explanatory power
- `customer_rating` — had missing data; marginal contribution after controlling for other factors
- `monthly_profit` — outcome variable, not a predictor
- `store_id`, `month`, `store_type`, `region` — replaced by dummy variables or identifiers

---

## Regression Approach

Three regression models were built:

1. **Model 1 (Simple Regression):** `footfall → monthly_sales`  
   - R² = 0.7363 | P-value < 0.001 | Strongest single predictor

2. **Model 2 (Simple Regression):** `marketing_spend → monthly_sales`  
   - R² = 0.1672 | P-value < 0.001 | Weak explanatory power in isolation

3. **Model 3 (Multiple Regression — Final Model):** All key numerical and dummy variables  
   - R² = 0.8296 | Adjusted R² = 0.8240 | 9 of 10 predictors significant

All regressions used Ordinary Least Squares (OLS). P-values and standard errors were calculated using the t-distribution.

---

## Dummy Variable Approach

**Region variable:** 4 categories (East, North, South, West)  
→ Created 3 dummies: `region_North`, `region_South`, `region_West`  
→ **Reference category: East** (dropped to avoid multicollinearity)

**Store Type variable:** 4 categories (Residential, High Street, Mall, Airport)  
→ Created 3 dummies: `store_Mall`, `store_High_Street`, `store_Airport`  
→ **Reference category: Residential** (dropped to avoid multicollinearity)

Dummy coefficients represent the sales premium or discount for each category **relative to the reference category**, after controlling for all other variables.

---

## Model Comparison Summary

| Model | R-squared | Adj R² | Significant Variables | Recommended? |
|-------|-----------|--------|-----------------------|--------------|
| Simple — Footfall | 0.7363 | N/A | 1/1 | Partial |
| Simple — Marketing | 0.1672 | N/A | 1/1 | No |
| **Multiple Regression** | **0.8296** | **0.8240** | **9/10** | **YES** |

---

## Final Model Selected

**Model 3: Multiple Regression**

**Equation:**
```
monthly_sales = 86,436
              + 28.83 × footfall
              + 1.17 × marketing_spend
              + 2,790 × staff_count
              + 3,003 × inventory_availability_pct
              + 7,601 × region_North
              + 20,901 × region_South
              + 18,893 × region_West
              + 29,594 × store_Mall
              + 17,402 × store_High_Street
              + 39,934 × store_Airport
```

**Reason:** Highest R² (0.83), most comprehensive coverage of business levers, 9 of 10 variables statistically significant, and adjusted R² confirms no overfitting.

---

## Business Recommendation

Three priority actions for leadership:

1. **Footfall First** — Redirect marketing investment to demonstrably footfall-driving campaigns (geotargeting, loyalty, local events). Footfall is the single strongest driver of sales.

2. **Inventory Excellence** — Set a 90%+ inventory availability target. Each 1% improvement is associated with £3,003 additional monthly sales — a high-return operational lever.

3. **Format & Location Optimisation** — Prioritise Airport and Mall formats in estate planning. Airport stores generate approximately £39,934 more per month than Residential stores, all else equal.

---

## Assumptions and Limitations

- Relationships are assumed to be **linear** — diminishing returns at extreme values are not captured
- Model shows **association, not causation** — controlled experiments are needed to establish causal claims
- Based on only **4 months of data** — seasonal and long-term trends not fully captured
- **Unmeasured variables** (management quality, local demographics, weather, one-off events) influence sales but are absent from the model
- Missing values were imputed with medians — this may introduce minor bias
- Regression does not account for **within-store correlation** across months (panel data methods would be more rigorous)

---

## Screenshots Included

| Screenshot File | Content |
|-----------------|---------|
| `screenshots/simple_regression_output.png` | Simple regression output — footfall model |
| `screenshots/multiple_regression_output.png` | Multiple regression coefficients table |
| `screenshots/residuals_preview.png` | Predicted values and residuals table |
| `screenshots/model_comparison_preview.png` | Model comparison table |

---

## Repository Structure

```
part3_regression_insights/
├── data/
│   └── business_regression_data.xlsx
├── analysis/
│   ├── regression_workbook.xlsx
│   ├── model_comparison.md
│   └── residual_analysis.md
├── outputs/
│   ├── regression_summary.xlsx
│   ├── final_recommendation.md
│   └── model_equations.md
├── screenshots/
│   ├── simple_regression_output.png
│   ├── multiple_regression_output.png
│   ├── residuals_preview.png
│   └── model_comparison_preview.png
└── README.md
```

---

## Tools Used

- **Python 3** — pandas, numpy, scipy.stats for data analysis and regression  
- **openpyxl** — Excel workbook creation with formatting  
- **Microsoft Excel / LibreOffice Calc** — Workbook review and screenshots  
- **Markdown** — Documentation  
- **Git / GitHub** — Version control and submission

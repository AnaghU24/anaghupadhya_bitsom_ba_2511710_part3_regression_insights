# Model Equations & Coefficient Explanations

## Overview

This document presents the regression equations developed for the retail chain monthly sales analysis, along with plain-language explanations of each coefficient, dummy variable handling, and the rationale for the final model selection.

---

## Simple Regression Equations

### Model 1: Footfall → Monthly Sales

**Equation:**
```
monthly_sales = 446,411 + 35.678 × footfall
```

| Term | Value | Business Meaning |
|------|-------|-----------------|
| Intercept | 446,411 | Theoretical baseline sales if no customers visited (not directly meaningful in isolation — all stores receive some footfall) |
| footfall coefficient | 35.678 | For every additional customer who walks into the store in a month, average monthly sales increase by approximately **£35.68** |
| R-squared | 0.7363 | Footfall alone explains 73.6% of the variation in monthly sales |
| P-value | < 0.001 | Extremely strong statistical confidence — this relationship is not due to chance |

**Business Language:** Stores that attract more visitors sell more. Every 1,000 additional monthly visitors is associated with approximately £35,678 more in monthly sales.

---

### Model 2: Marketing Spend → Monthly Sales

**Equation:**
```
monthly_sales = 560,777 + 2.1296 × marketing_spend
```

| Term | Value | Business Meaning |
|------|-------|-----------------|
| Intercept | 560,777 | Estimated baseline sales without any marketing investment |
| marketing_spend coefficient | 2.1296 | Each additional £1 spent on marketing is associated with approximately **£2.13** in additional monthly sales |
| R-squared | 0.1672 | Marketing spend alone explains only 16.7% of sales variation |
| P-value | < 0.001 | Statistically significant, but effect is weak when marketing is the only predictor |

**Business Language:** Marketing has a positive association with sales, but its impact is modest when measured in isolation. The return of £2.13 per £1 spent sounds positive, but this estimate is unreliable without controlling for other factors — stores that spend more may simply be bigger stores with more footfall.

---

## Multiple Regression Equation (Final Model)

**Full Equation:**
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

---

## Coefficient Explanations (Plain Language)

| Variable | Coefficient | Interpretation |
|----------|-------------|----------------|
| **Intercept** | 86,436 | Baseline estimated sales for a Residential store in East region, with all numeric predictors at zero — a mathematical anchor, not a real prediction |
| **footfall** | 28.83 | After controlling for all other factors, each additional monthly visitor adds approximately **£28.83** to sales. This is the strongest single lever. |
| **marketing_spend** | 1.17 | Each additional £1 of marketing is associated with **£1.17** more in sales, after accounting for footfall and other variables. Return above £1 is positive but modest. |
| **staff_count** | 2,790 | Each additional staff member on the team is associated with **£2,790** more in monthly sales. More staff enables better service and higher conversion. |
| **inventory_availability_pct** | 3,003 | Each 1% improvement in inventory availability is associated with approximately **£3,003** more in sales — strong evidence that stock-outs cost revenue. |
| **region_North** | 7,601 | North region stores generate £7,601 more than East region stores on average, **but this is not statistically significant (p=0.281)** — could be due to random variation |
| **region_South** | 20,901 | South region stores generate approximately **£20,901 more** than East region stores, statistically significant (p=0.003) |
| **region_West** | 18,893 | West region stores generate approximately **£18,893 more** than East region stores, statistically significant (p=0.003) |
| **store_Mall** | 29,594 | Mall stores generate approximately **£29,594 more** per month than Residential stores, all else equal — significant (p<0.001) |
| **store_High_Street** | 17,402 | High Street stores generate approximately **£17,402 more** than Residential stores — significant (p=0.004) |
| **store_Airport** | 39,934 | Airport stores generate approximately **£39,934 more** than Residential stores — the **largest format premium**, very significant (p<0.001) |

---

## Dummy Variable Explanation

### What Are Dummy Variables?

Categorical variables like `region` (East, North, South, West) and `store_type` (Residential, High Street, Mall, Airport) cannot be directly entered into a regression model as text. They must be converted into binary (0/1) numeric columns — one column per category. This is called **dummy variable encoding**.

### Why Drop One Category?

If we include a dummy for every category, the variables become **perfectly collinear** — one can always be derived from the others. This causes a mathematical failure in the regression (the "dummy variable trap"). We drop one category from each group — the **reference category** — and all other dummies are interpreted relative to it.

### Reference Categories Used

| Variable Group | Reference Category | Reason for Choice |
|---------------|-------------------|-------------------|
| **region** | **East** | East is the most common region type in the dataset and serves as a neutral baseline |
| **store_type** | **Residential** | Residential is the most common store format — a natural baseline for comparison |

### How to Interpret Dummy Coefficients

The coefficient on `store_Airport` (= 39,934) means:
> *"An Airport store is expected to generate £39,934 more in monthly sales than an otherwise identical Residential store."*

If `store_Airport = 0` and `store_Mall = 0` and `store_High_Street = 0`, the store is implicitly Residential (the reference category).

---

## Final Model Selected

**Model 3: Multiple Regression**

**Reason for Selection:**

1. **Highest explanatory power** — R² = 0.8296 vs 0.7363 and 0.1672 for simple models  
2. **Comprehensive coverage** — includes footfall, marketing, staffing, inventory, and structural store characteristics  
3. **Statistically robust** — 9 of 10 predictors are statistically significant at p < 0.05  
4. **Business actionability** — provides specific guidance on which levers to pull (inventory, footfall, store type investment)  
5. **Minimal overfitting** — Adjusted R² (0.8240) is close to R² (0.8296), confirming added variables are genuinely useful  

This model forms the evidence base for the Final Recommendation report.

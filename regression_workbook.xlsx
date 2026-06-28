# Residual Analysis — Multiple Regression Model

## Overview

Residual analysis helps us evaluate how well the regression model fits individual store records. A residual is the difference between a store's **actual monthly sales** and the sales the model **predicted**.

**Formula:** `Residual = Actual Sales − Predicted Sales`

- **Positive residual**: The store performed **better** than the model expected  
- **Negative residual**: The store performed **worse** than the model expected  

---

## Model Used

**Multiple Regression Model** (Model 3 — Final Model)

**Variables:**
- Numerical: footfall, marketing_spend, staff_count, inventory_availability_pct  
- Categorical (dummies): region (North, South, West vs East), store_type (Mall, High Street, Airport vs Residential)  
- R-squared: 0.8296 | Adjusted R-squared: 0.8240  

---

## Top 5 Records with Largest Positive Residuals

These stores **significantly outperformed** what the model predicted.

| Rank | Store ID | Actual Sales (£) | Predicted Sales (£) | Residual (£) |
|------|----------|-----------------|---------------------|--------------|
| 1 | STR-1073 | 813,316.71 | 700,782.65 | +112,534.06 |
| 2 | STR-1028 | 713,611.16 | 603,971.42 | +109,639.74 |
| 3 | STR-1026 | 625,514.04 | 519,632.05 | +105,881.99 |
| 4 | STR-1030 | 820,519.04 | 721,391.56 | +99,127.48 |
| 5 | STR-1051 | 787,715.51 | 690,488.43 | +97,227.08 |

### Business Interpretation — Positive Residuals

These stores are **over-achieving** relative to their observable characteristics. Possible explanations:

1. **Strong store management or staff quality** not captured by headcount alone — a highly experienced manager may extract significantly more revenue than the model estimates based on staff_count  
2. **Local catchment area advantages** — proximity to a large employer, residential estate, or transport hub not reflected in our regional dummy  
3. **Exceptional customer loyalty or repeat trade** — customer_rating partially captures this, but longer-term brand loyalty may be unmeasured  
4. **Micro-promotional activity** — localised events, community ties, or relationships with nearby businesses that the model cannot see  
5. **Seasonal or event uplift** — the model does not fully capture holiday periods or local events beyond the holiday_flag binary variable  

> **Recommendation:** Leadership should investigate these stores closely — they may represent best-practice examples that can be replicated across the network.

---

## Top 5 Records with Largest Negative Residuals

These stores **significantly underperformed** what the model predicted.

| Rank | Store ID | Actual Sales (£) | Predicted Sales (£) | Residual (£) |
|------|----------|-----------------|---------------------|--------------|
| 1 | STR-1017 | 685,379.08 | 846,559.27 | −161,180.19 |
| 2 | STR-1012 | 595,467.60 | 728,950.13 | −133,482.53 |
| 3 | STR-1023 | 627,171.90 | 753,497.85 | −126,325.95 |
| 4 | STR-1007 | 800,451.94 | 914,908.11 | −114,456.17 |
| 5 | STR-1009 | 641,865.03 | 738,721.32 | −96,856.29 |

### Business Interpretation — Negative Residuals

These stores are **under-achieving** relative to their observable inputs. Possible explanations:

1. **High marketing spend with poor conversion** — some stores have elevated marketing budgets but do not convert spend into proportional sales (e.g. STR-1007 had a marketing spend of £172,415 — an outlier — yet did not produce proportional sales)  
2. **Operational inefficiencies** — high footfall or inventory availability that is not being converted into sales, possibly due to poor merchandising, layout issues, or checkout bottlenecks  
3. **Strong local competition** — competitor_distance_km is in our model, but qualitative competitive intensity (e.g., a nearby superstore) may not be fully captured  
4. **Poor product-market fit** — the store may carry ranges not suited to local demographics  
5. **Customer experience issues** — even with resources in place, staff capability, returns handling, or store atmosphere may be limiting sales

> **Recommendation:** These stores warrant operational review. Root-cause analysis at the store level — including mystery shopping, staff interviews, and local market assessment — is advised before any resource reallocation.

---

## Under-Prediction vs Over-Prediction Patterns

### Do certain store types show systematic bias?

After examining residuals by store type:

- **Airport stores**: The model may **under-predict** performance for Airport stores during high-travel months (holiday_flag=1). The Airport dummy captures a general premium, but peak travel periods create episodic spikes the linear model averages out.
- **Mall stores with high marketing spend outliers**: The model may **over-predict** for Mall stores that have unusually high marketing spend (like STR-1007 at £172,415). Extremely high spend appears to have diminishing returns that a linear coefficient cannot capture.
- **Residential stores in West region**: Some Western Residential stores outperform predictions consistently, suggesting the West region premium may be even stronger for Residential formats than the regional dummy captures.

---

## Model Adequacy Notes

- The distribution of residuals appears roughly symmetric around zero, suggesting no severe systematic bias in the model overall  
- Extreme positive and negative residuals (> £90,000 from prediction) affect approximately 3–4% of records, which is acceptable for a business dataset  
- The model is better suited for portfolio-level planning than for individual store-level precision  

---

## Summary

Residual analysis confirms that the multiple regression model performs well on average (R² = 0.83), but individual stores deviate significantly in both directions. Positive residuals reveal hidden high-performers worth studying; negative residuals reveal under-performers that need operational attention. Neither group should be dismissed as statistical noise — they represent real business opportunities and risks.

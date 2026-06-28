# Model Comparison Analysis

## Overview

Three regression models were developed to explain monthly sales variation across stores. This document compares each model on key statistical and business dimensions.

---

## Model Descriptions

### Model 1: Simple Regression — Footfall
| Item | Detail |
|------|--------|
| **Model Name** | Simple Regression — Footfall |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | footfall |
| **R-squared** | 0.7363 |
| **Coefficient** | 35.678 |
| **P-value** | < 0.001 (highly significant) |
| **Equation** | monthly_sales = 446,411 + 35.68 × footfall |

**Business Interpretation:**  
Footfall alone explains **73.6%** of monthly sales variation — the strongest single predictor. Each additional visitor is associated with approximately £35.68 in additional monthly sales. This makes intuitive sense: more customers in-store leads to more transactions. This model is excellent for a quick understanding but ignores all other business levers.

**Limitations:**  
- Ignores marketing, staff, inventory, and store characteristics  
- Cannot guide decisions beyond driving foot traffic  
- Does not account for regional differences  

---

### Model 2: Simple Regression — Marketing Spend
| Item | Detail |
|------|--------|
| **Model Name** | Simple Regression — Marketing Spend |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | marketing_spend |
| **R-squared** | 0.1672 |
| **Coefficient** | 2.1296 |
| **P-value** | < 0.001 (statistically significant) |
| **Equation** | monthly_sales = 560,777 + 2.13 × marketing_spend |

**Business Interpretation:**  
Marketing spend is statistically significant but only explains **16.7%** of sales variation. Each £1 extra in marketing spend is associated with approximately £2.13 in additional monthly sales, implying a positive but modest return. When looked at alone, marketing is a weak predictor, suggesting its impact is conditional on other factors like footfall and store type.

**Limitations:**  
- Very low R² (16.7%) — most variation unexplained  
- Returns on marketing likely vary by store type and region  
- Cannot be used in isolation for strategic decisions  

---

### Model 3: Multiple Regression (Final Model)
| Item | Detail |
|------|--------|
| **Model Name** | Multiple Regression — All Key Drivers |
| **Dependent Variable** | monthly_sales |
| **Independent Variables** | footfall, marketing_spend, staff_count, inventory_availability_pct, region dummies (North, South, West vs East), store type dummies (Mall, High Street, Airport vs Residential) |
| **R-squared** | 0.8296 |
| **Adjusted R-squared** | 0.8240 |
| **Significant Variables** | footfall (p<0.001), marketing_spend (p<0.001), staff_count (p=0.027), inventory_availability_pct (p<0.001), region_South (p=0.003), region_West (p=0.003), store_Mall (p<0.001), store_High_Street (p=0.004), store_Airport (p<0.001) |
| **Non-significant** | region_North (p=0.281) |

**Business Interpretation:**  
This model explains **82.96%** of monthly sales variation — a substantial improvement over either simple model. All major business levers are included. The model confirms that footfall, inventory availability, store type, and region all independently drive sales. Airport and Mall stores outperform Residential stores even after controlling for footfall and other factors.

**Limitations:**  
- Association, not causation — spending more on marketing does not guarantee proportionally higher sales  
- Model cannot account for local competitive dynamics or one-off events  
- region_North is statistically indistinguishable from region_East — may need more data or granular regional variables  

---

## Head-to-Head Comparison Table

| Criterion | Model 1 (Footfall) | Model 2 (Marketing) | Model 3 (Multiple) |
|-----------|-------------------|---------------------|-------------------|
| R-squared | 0.7363 | 0.1672 | **0.8296** |
| Adj. R-squared | N/A | N/A | **0.8240** |
| Variables | 1 | 1 | 10 |
| Significant Vars | 1/1 | 1/1 | 9/10 |
| Business Coverage | Narrow | Narrow | **Comprehensive** |
| Actionability | Limited | Limited | **High** |
| Model Complexity | Low | Low | Moderate |
| Recommended | Partial | No | **YES** |

---

## P-value & R-squared Interpretation

- **R-squared** measures how much of sales variation the model explains. A higher value means the model fits the data better. Model 3 at 0.83 is strong for business data.
- **P-value < 0.05** means the variable is statistically significant — the relationship is unlikely to be due to chance. All variables in Model 3 except region_North are significant.
- **Adjusted R-squared** penalises for adding variables that do not improve fit. The small difference (0.8296 vs 0.8240) confirms all added variables are genuinely useful.

---

## Conclusion

**Model 3 (Multiple Regression)** is the superior model. It combines statistical strength (R² = 0.83), comprehensive business coverage, and actionable insights across footfall, marketing spend, inventory, store type, and region. Leadership should use this model for strategy decisions rather than relying on any single-factor model.

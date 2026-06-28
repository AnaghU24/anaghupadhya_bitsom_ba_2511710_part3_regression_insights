# Final Business Recommendation

## Executive Summary

Based on regression analysis of 320 store-month observations across 80 stores and 4 months, we have identified the key drivers of monthly sales performance for the retail chain. The analysis used multiple regression (R² = 0.83) to provide evidence-based recommendations for leadership action.

---

## 1. Which Factors Appear Most Strongly Associated with Monthly Sales?

In order of statistical strength and business impact:

| Rank | Factor | Coefficient | P-value | Impact |
|------|--------|-------------|---------|--------|
| 1 | **Footfall** | +£28.83 per visitor | < 0.001 | Very High |
| 2 | **Store Type: Airport** | +£39,934 vs Residential | < 0.001 | Very High |
| 3 | **Store Type: Mall** | +£29,594 vs Residential | < 0.001 | High |
| 4 | **Inventory Availability (%)** | +£3,003 per 1% improvement | < 0.001 | High |
| 5 | **Marketing Spend** | +£1.17 per £1 spent | < 0.001 | Moderate |
| 6 | **Region: South** | +£20,901 vs East | 0.003 | Moderate |
| 7 | **Region: West** | +£18,893 vs East | 0.003 | Moderate |
| 8 | **Store Type: High Street** | +£17,402 vs Residential | 0.004 | Moderate |
| 9 | **Staff Count** | +£2,790 per additional staff | 0.027 | Moderate |
| 10 | **Region: North** | +£7,601 vs East | 0.281 | Weak / Insignificant |

---

## 2. Which Variables Should Leadership Focus On?

### Priority 1: Footfall (Drive More Customers In-Store)

**Evidence:** Footfall alone explains 73.6% of sales variation. In the multiple regression model, each additional monthly visitor adds £28.83 to sales.

**Action:** Invest in localised footfall-driving initiatives — events, loyalty schemes, digital geotargeting campaigns, and community partnerships near store locations. Marketing spend that increases footfall will have a multiplied effect on sales compared to brand-level marketing.

---

### Priority 2: Inventory Availability

**Evidence:** Each 1% improvement in inventory availability is associated with £3,003 more in monthly sales (p < 0.001). This is one of the highest-value interventions per unit of operational effort.

**Action:** Reduce stock-outs by improving replenishment frequency, optimising safety stock levels, and investing in demand forecasting tools. A store improving from 80% to 90% inventory availability is expected to generate approximately £30,000 more per month — a very significant uplift.

---

### Priority 3: Store Type & Format Positioning

**Evidence:** Airport stores outperform Residential stores by £39,934/month and Mall stores by £29,594/month on average, all else being equal.

**Action:** When evaluating new store openings or lease renewals, prioritise Airport and Mall locations. When investing in existing estates, Mall and High Street stores offer structurally higher revenue potential than Residential formats.

---

### Priority 4: Regional Strategy (South & West)

**Evidence:** South and West region stores generate approximately £20,901 and £18,893 more per month than East region stores respectively.

**Action:** Consider allocating higher marketing budgets, additional staff, or expanded product ranges to South and West stores, where the market conditions appear more favourable. Investigate what drives this regional advantage — it may be demographic, competitive, or operational.

---

### Priority 5: Staff Count

**Evidence:** Each additional staff member is associated with £2,790 more in monthly sales (p = 0.027).

**Action:** Understaffed stores may be losing sales through poor service, slow checkout, and reduced floor coverage. An audit of staff-to-footfall ratios across stores could identify where incremental staffing investment would pay back through sales uplift.

---

## 3. Which Variables Should Not Be Over-Interpreted?

### Marketing Spend (in isolation)

**Finding:** The simple regression of marketing spend on sales only explains 16.7% of variation. In the multiple model, the coefficient is £1.17 per £1 spent — suggesting modest returns when other factors are held constant.

**Caution:** This does not mean marketing is ineffective. Marketing likely works by driving footfall, and the model partially accounts for this by including footfall separately. However, leadership should not assume that simply increasing marketing spend will proportionally boost sales. The mechanism matters — targeted campaigns that drive in-store visits will outperform generic brand spend.

### Region: North (p = 0.281)

**Finding:** The North region coefficient is not statistically significant. We cannot confidently say North stores perform differently from East stores based on this data.

**Caution:** Do not make North-specific resource decisions based on this variable alone. More data or a more granular local analysis would be needed.

### avg_discount_pct

**Finding:** Discount percentage was not included in the final model because its correlation with sales in exploratory analysis was inconsistent — some stores ran high discounts and still achieved high sales, while others did not. Including it added noise without improving model fit.

**Caution:** Discounting strategy requires a separate margin analysis. Regression on total sales alone cannot evaluate whether discounts are profitable.

---

## 4. What Business Action Would We Recommend?

Based on the regression evidence, we recommend a **Three-Pillar Action Plan:**

### Pillar 1 — Footfall First
Redirect at least 50% of the marketing budget toward initiatives that demonstrably drive in-store visits (digital geofencing, loyalty points, in-store events, local partnerships). Establish a footfall KPI at the store level and track it monthly.

### Pillar 2 — Inventory Excellence
Set a minimum inventory availability target of 90% across all stores. Invest in supply chain visibility tools and fast-replenishment contracts with key suppliers. Pilot automated reordering in the 10 stores with the lowest current availability scores.

### Pillar 3 — Format & Location Optimisation
In the next estate review cycle, prioritise Airport and Mall locations for new openings or expanded space. For underperforming Residential stores in the East region, evaluate whether relocation or format conversion is viable.

---

## 5. What Risks or Limitations Should Leadership Keep in Mind?

| Risk | Explanation |
|------|-------------|
| **Correlation ≠ Causation** | The model shows associations, not cause-and-effect. Increasing marketing spend by £10,000 will not automatically generate £11,700 in sales — other factors must align |
| **Reverse causality** | High-sales stores may attract more investment (staff, marketing), making causality hard to establish from observational data alone |
| **Omitted variables** | The model cannot capture management quality, local competitor behaviour, seasonal product range changes, or weather effects — all of which may influence sales |
| **Linearity assumption** | The model assumes relationships are linear. In reality, returns to footfall or marketing may diminish at very high levels (as seen in STR-1007's high marketing spend with unexpectedly modest sales) |
| **Model is historical** | The model is built on 4 months of 2025 data. Economic conditions, consumer behaviour, and competitive dynamics may shift, requiring the model to be updated periodically |
| **Within-store variation unexplained** | The model explains 83% of variation — but 17% remains unexplained. Individual store decisions should not rely solely on model predictions |

---

## 6. Why Does Regression Show Association But Not Automatically Prove Causation?

Regression identifies **statistical relationships** in historical data. It tells us that when footfall is higher, sales tend to be higher. But it cannot tell us **why** this is the case or whether **intervening on footfall will produce the same result**.

Key reasons causation cannot be assumed:

1. **Confounding variables**: A third unmeasured factor (e.g. a major employer nearby) could be driving both footfall and sales simultaneously — making footfall look causal when it is merely correlated.

2. **Reverse causality**: High-performing stores may invest more in marketing and staff, not the other way around. The data looks the same either way in a simple regression.

3. **Selection effects**: Airport stores are in airports because of commercial decisions — they do not "become" Airport stores randomly. Comparing them to Residential stores via regression cannot control for all the differences between those contexts.

4. **Historical data only**: The regression reflects what happened, not what would happen under new conditions or deliberate interventions.

To establish causation, the business would need **controlled experiments** — for example, randomly assigning different marketing budgets or inventory targets to stores and measuring the impact. Regression is the starting point for identifying where to experiment, not the proof that interventions will work.

---

## Final Conclusion

The multiple regression model provides strong evidence that **footfall, inventory availability, store format, and region** are the primary determinants of monthly sales performance. Leadership should prioritise footfall-driving initiatives and inventory excellence as the highest-return interventions, while using format and regional insights to guide capital allocation. All recommendations should be validated through controlled pilots before network-wide rollout.

*Regression evidence supports direction of investment — execution quality, local market conditions, and ongoing measurement will determine actual outcomes.*

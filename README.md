# 📊 A/B Testing Case Study
### Evaluating the Impact of Paid Advertisements on Conversion

---

## Table of Contents

1. [Business Context](#1-business-context)
2. [Experimental Design](#2-experimental-design)
3. [Data Overview](#3-data-overview)
4. [Data Validation & Quality Checks](#4-data-validation--quality-checks)
5. [Statistical Testing](#5-statistical-testing)
6. [Confidence Intervals](#6-confidence-intervals)
7. [Effect Size & Lift](#7-effect-size--lift)
8. [Incremental Impact Analysis](#8-incremental-impact-analysis)
9. [Revenue Estimation](#9-revenue-estimation)
10. [Statistical Power Analysis](#10-statistical-power-analysis)
11. [Strategic Interpretation](#11-strategic-interpretation)
12. [Risk & Platform Considerations](#12-risk--platform-considerations)
13. [Final Decision](#13-final-decision)
14. [Key Learnings](#14-key-learnings)
15. [Advanced ROI Analysis](#advanced-roi-analysis)
16. [Exposure & Frequency Analysis](#exposure--frequency-analysis)
17. [Interview-Ready Summary](#interview-ready-summary)

---

## 1. Business Context

A marketing team wanted to evaluate whether paid advertisements meaningfully increase product purchase conversions compared to showing a Public Service Announcement (PSA).

**Key strategic questions:**

| # | Question |
|---|----------|
| 1 | Does exposure to advertisements increase conversion rate? |
| 2 | Is the observed difference statistically significant? |
| 3 | Is the lift economically meaningful? |
| 4 | Should the campaign be scaled? |

---

## 2. Experimental Design

| Component | Detail |
|-----------|--------|
| **Design Type** | Randomized Controlled Experiment (RCT) |
| **Treatment Group** | Exposed to advertisement |
| **Control Group** | Exposed to PSA |
| **Primary Metric** | Conversion Rate (Binary: Converted / Not Converted) |
| **Test Type** | Two-sided Z-test (conservative inference) |

**Hypotheses:**

```
H₀ (Null):        p_ad = p_psa
H₁ (Alternative): p_ad > p_psa
```

---

## 3. Data Overview

| Group | Users | Conversions | Conversion Rate |
|-------|-------|-------------|-----------------|
| **Ad (Treatment)** | 564,577 | 14,423 | **2.55%** |
| **PSA (Control)** | 23,524 | 420 | **1.79%** |

> **Note:** Control group was intentionally smaller (~4% of total) for cost efficiency.

---

## 4. Data Validation & Quality Checks

| Check | Status | Finding |
|-------|--------|---------|
| Missing Values | ✅ Pass | No missing values in assignment or conversion |
| Conversion Validity | ✅ Pass | Binary conversion variable properly formatted |
| Sample Ratio Check | ⚠️ Flagged | Imbalanced vs 50/50 split — intentional by design |

> **Conclusion:** No unexpected assignment error detected. Skew toward treatment was deliberate.

---

## 5. Statistical Testing

**Test Used:** Two-Proportion Z-Test

| Metric | Value |
|--------|-------|
| **Z-statistic** | 7.37 |
| **P-value** | < 0.000001 |
| **Decision** | ✅ Reject H₀ |

> The probability of observing this lift under the null hypothesis is effectively zero.

---

## 6. Confidence Intervals

**95% Confidence Intervals:**

| Group | Lower Bound | Upper Bound |
|-------|-------------|-------------|
| **Ad** | 2.51% | 2.59% |
| **PSA** | 1.62% | 1.95% |

> Non-overlapping intervals indicate **strong separation** between groups.

---

## 7. Effect Size & Lift

**Absolute Lift:**
```
2.55% - 1.79% = 0.77 percentage points
```

**Relative Lift:**
```
0.77 / 1.79 ≈ 43%
```

> This represents a **43% improvement** in conversion relative to the baseline PSA group.

---

## 8. Incremental Impact Analysis

| Metric | Value |
|--------|-------|
| Expected conversions (if treated like control) | ~10,080 |
| Actual conversions | 14,423 |
| **Incremental conversions** | **~4,342** |

---

## 9. Revenue Estimation

> Assumption: Average Order Value (AOV) = **$100**

```
Incremental Revenue = 4,342 × $100 = $434,200
```

> This demonstrates both **statistical and financial significance**.

---

## 10. Statistical Power Analysis

| Metric | Value |
|--------|-------|
| Observed Power | ~100% |
| Required sample for 80% power | ~5,500 per group |

> Experiment was **highly powered** due to large sample size.

---

## 11. Strategic Interpretation

**From a statistical standpoint:**
- ✅ Strong significance
- ✅ Large Z-score (7.37)
- ✅ Narrow, non-overlapping confidence intervals

**From a business standpoint:**
- ✅ High relative lift (43%)
- ✅ Meaningful revenue impact (~$434K)
- ✅ Scalable opportunity

---

## 12. Risk & Platform Considerations

- No evidence of logging inconsistency
- Independent user-level assignment assumed
- Large treatment exposure supports scalability
- **Future recommendation:** Test ad frequency optimization

---

## 13. Final Decision

> 🚀 **Recommendation: Scale the advertisement campaign.**

**Further optimization should focus on:**
- Ad frequency impact
- Segment-level heterogeneity
- Time-of-day optimization

---

## 14. Key Learnings

1. Small absolute differences can produce large **relative lift**
2. Statistical significance must be paired with **business evaluation**
3. Sample size design heavily influences **detection power**
4. Structured experimentation enables **confident strategic decisions**

---

---

# Advanced ROI Analysis

## ROI Step 1 — Incremental Revenue

```
Incremental Conversions  = 4,342
Average Order Value      = $100
Incremental Revenue      = 4,342 × $100 = $434,200
```

---

## ROI Step 2 — Gross Profit Impact

> Revenue is not profit. Assumption: **Gross margin = 40%**

```
Gross Profit = $434,200 × 0.40 = $173,680
```

Real contribution profit ≈ **$173.7K**

---

## ROI Step 3 — Cost of Running Ads

> Assumptions:
> - Cost per ad impression = **$0.02**
> - Treatment users = **564,577**
> - Average ads per user = **50**

```
Total Impressions = 564,577 × 50 = 28,228,850
Ad Cost           = 28,228,850 × $0.02 = $564,577
```

Total ad cost ≈ **$564K**

---

## ROI Step 4 — Net Profit Impact

```
Net Profit = Gross Profit - Ad Cost
           = $173,680 - $564,577
           = -$390,897
```

> ⚠️ **Critical insight:** If ads are too expensive, conversion lift alone does **not** guarantee profitability.

---

## ROI Step 5 — Break-Even Analysis

Solving for the required margin to break even:

```
$434,200 × Margin ≥ $564,577
Margin ≥ 564,577 / 434,200
Margin ≥ 130%
```

> ❌ **Impossible.** At $0.02/impression and 50 exposures/user, the campaign is **not profitable** at 40% margin.

---

## ROI Step 6 — Sensitivity Analysis

### Scenario A — Lower Ad Cost ($0.005/impression)

```
Ad Cost    = 28,228,850 × $0.005 = $141,144
Net Profit = $173,680 - $141,144 = +$32,536  ✅ Profitable
```

### Scenario B — Higher AOV ($150)

```
Revenue      = 4,342 × $150      = $651,300
Gross Profit = $651,300 × 0.40   = $260,520
Net Profit   = $260,520 - $564,577 = -$304,057  ❌ Still negative
```

> **Key takeaway:** AOV improvement alone is insufficient at high ad cost — **reducing CPM is the critical lever.**

---

## ROI Step 7 — Annualized Projection

> Assumption: this traffic represents one month of activity.

| Metric | Value |
|--------|-------|
| Annual Incremental Revenue | $434,200 × 12 = **$5.2M** |
| Annual Gross Profit (40%) | $173,680 × 12 = **$2.08M** |

Scale impact becomes highly significant at the annual level.

---

## ROI Step 8 — Payback Period

> Assumption: Implementation cost = $50,000, Monthly net profit = $32,536 (profitable scenario)

```
Payback Period = $50,000 / $32,536 ≈ 1.5 months
```

> Very attractive ROI timeline. ✅

---

## ROI Step 9 — Customer Lifetime Value (LTV) Perspective

> Assumption: Acquired customers repeat purchase **3 times**

```
True Revenue Impact = $434,200 × 3 = $1.3M
```

> Short-term A/B testing may **significantly underestimate** true campaign value when LTV is factored in.

---

---

# Exposure & Frequency Analysis

## Chart 1 — Decile Analysis (Exposure Segmentation)
<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/59441555-8ae7-42ba-97e3-89144e7431e7" />

**What the data shows:**
- Conversion rate increases steadily with ad exposure
- Top exposure decile shows a dramatic spike in conversion
- Strong positive correlation between exposure and purchase likelihood

**Strategic Insights:**

| Signal | Implication |
|--------|-------------|
| ✅ Frequency drives conversion | Higher-exposure users convert significantly more |
| ✅ Top decile performance | High-frequency viewers are most likely to purchase |
| ⚠️ Top decile spike | May reflect high-intent users (selection bias risk) |

---

## Chart 2 — Diminishing Returns Curve

**What the data shows:**
- Conversion rises sharply up to **~80–100 ads**
- After **~100 exposures**, the curve flattens
- After **~120–150 exposures**, volatility increases significantly

**Interpretation:**

This is a classic **diminishing marginal returns** pattern:
<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/24dd3f60-c07a-47f6-894e-aeb564ae5483" />

| Exposure Range | Effect |
|----------------|--------|
| Early exposures (0–80) | Strong incremental conversion impact |
| Mid exposures (80–120) | Smaller marginal gains |
| Late exposures (120+) | High noise, potential over-saturation |

> **Business Recommendation:** Optimal ad frequency is likely between **60–100 impressions**. Beyond that, budget efficiency declines and user fatigue risk increases.

---

## Chart 3 — Cumulative Lift Curve
<img width="584" height="455" alt="image" src="https://github.com/user-attachments/assets/b0942f9b-e1e0-4b85-bcfa-525bb52f5a85" />

**What the data shows:**
- Rapid cumulative conversion growth in early exposure
- Gradual flattening toward overall average (~2.5%)

**Confirms:**
- ✅ Early exposure drives the **majority** of incremental impact
- ✅ Later exposures add **marginal** incremental value

---

---

## Interview-Ready Summary

> *"I conducted a full end-to-end A/B test evaluating advertisement impact on conversion. Using a two-proportion Z-test, I found a statistically significant 0.77 percentage point lift — a 43% relative improvement. The result was highly significant (Z = 7.37, p < 0.001) with an estimated 4,342 incremental conversions, translating to approximately $434K in incremental revenue.*
>
> *While the experiment demonstrated strong statistical validity, profitability analysis revealed that ROI depends heavily on cost per impression and margin assumptions. Under optimized acquisition costs ($0.005/impression), the campaign becomes profitable with strong annualized impact (~$2M gross profit). This highlights the importance of integrating statistical validation with financial modeling before scaling — and why frequency capping between 60–100 impressions is the recommended next optimization lever."*

---

*Built with structured experimentation and financial rigor. Combining statistical significance with business impact analysis for confident, scalable decisions.*

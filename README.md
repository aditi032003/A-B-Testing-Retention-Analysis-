# 🎮 A/B Testing: Impact of Progression Gate on Player Retention

## 📌 Project Overview

Cookie Cats uses progression gates where players must wait or make an in-app purchase before continuing. The product team tested whether moving the first gate from level 30 to level 40 would improve player experience and increase retention.

The main business question was:

**Should the company move the first progression gate from level 30 to level 40?**

![image alt](https://github.com/aditi032003/A-B-Testing-Retention-Analysis-/blob/9886910381e64b9a0dbebf1c549535c37957e476/Screenshot%202026-10-06%20205907.png)

---

## 🎯 Business Questions

This analysis answers:

1. Were the two experiment groups reasonably balanced?
2. Did moving the gate affect **Day-1 retention**?
3. Did it affect **Day-7 retention**?
4. Could the observed differences be explained by random variation?
5. What is the practical impact at scale?
6. Should the company ship the change?

---

## 🗂️ Dataset

**Dataset:** Cookie Cats Mobile Games A/B Testing  
**Players:** ~90,000

| Group | Description |
|---|---|
| Gate 30 | Control group |
| Gate 40 | Treatment group |

The dataset contains player-level information including:

- User ID
- Experiment version
- Total game rounds played
- Day-1 retention
- Day-7 retention

---

# 🧹 Data Preparation

Before comparing the two groups:

- Checked for duplicate users
- Reviewed the distribution of game rounds
- Removed one obvious and implausible game-round anomaly
- Used the cleaned dataset for the final analysis

After cleaning, the analysis contained **90,188 players**.

| Group | Players | Share |
|---|---:|---:|
| Gate 30 | 44,699 | 49.56% |
| Gate 40 | 45,489 | 50.44% |

The groups were broadly balanced, supporting comparison of retention outcomes.

---

# 📊 Retention Results

## Day-1 Retention

| Metric | Gate 30 | Gate 40 |
|---|---:|---:|
| Retention | 44.82% | 44.23% |
| Difference | | **-0.59 pp** |
| p-value | | **7.39%** |
| 95% CI | | **-1.24 pp to +0.06 pp** |

### What this means

Gate 40 had slightly lower Day-1 retention, but the difference was **not statistically significant at the 5% level**.

The confidence interval includes zero, meaning the data is consistent with both a small negative effect and essentially no effect.

**Conclusion:** No strong evidence that Gate 40 changed Day-1 retention.

---

## Day-7 Retention

| Metric | Gate 30 | Gate 40 |
|---|---:|---:|
| Retention | 19.02% | 18.20% |
| Difference | | **-0.82 pp** |
| p-value | | **0.159%** |
| 95% CI | | **-1.33 pp to -0.31 pp** |

### What this means

Gate 40 had lower Day-7 retention, and the difference was **statistically significant**.

The entire confidence interval is below zero, providing stronger evidence that the treatment negatively affected longer-term observed retention.

**Conclusion:** Gate 40 is associated with a meaningful decline in Day-7 retention.

---

# 📈 Bootstrap Analysis

To understand how much the estimated retention gap could vary, I simulated **10,000 bootstrap samples** and calculated the retention gap for each simulation.

The bootstrap distribution shows where the estimated retention difference tends to fall across repeated samples.

![image alt](https://github.com/aditi032003/A-B-Testing-Retention-Analysis-/blob/5171d3d25ccca908f9e014ffdfe820ef4bd9f512/Screenshot%202026-10-06%20222658.png)

### Day-7 takeaway

The simulated Day-7 retention gaps are concentrated below zero, supporting the observed negative effect of approximately **-0.82 percentage points**.

This provides an intuitive view of the **uncertainty and variability around the estimated effect**, rather than relying only on a p-value.

---

# 💰 Practical Business Impact

A percentage-point difference can be translated into player impact.

If the observed differences were applied to a population of **1 million players**:

| Metric | Retention Gap | Approx. Player Impact |
|---|---:|---:|
| Day 1 | -0.59 pp | **~5,915 fewer retained players** |
| Day 7 | -0.82 pp | **~8,183 fewer retained players** |

These are hypothetical extrapolations based on the observed experiment effect, not actual measured player losses.

---

# 🚦 Recommendation

## ❌ Do not roll out Gate 40 based on retention alone.

The experiment provides:

- No statistically significant Day-1 retention difference
- A statistically significant negative Day-7 retention difference
- An estimated Day-7 decline of approximately **0.82 percentage points**
- A potential impact of approximately **8,183 fewer retained users per 1 million players**

Based on retention alone, the evidence does **not support moving the progression gate from Level 30 to Level 40**.

---

# ⚠️ Limitations

The experiment does not answer everything a product team would need to know.

### 1. Revenue impact

The dataset does not contain revenue or monetization metrics, so the analysis cannot determine whether Gate 40 affected:

- Revenue
- Purchases
- ARPU
- LTV

### 2. Longer-term retention

The available retention metrics are Day 1 and Day 7.

The analysis therefore cannot determine whether the effect persists beyond Day 7.

### 3. Longer-term user behaviour

The test cannot establish whether the observed retention difference represents a sustained product effect or changes over time.

---

# 🔎 What I Would Measure Next

Before making a final product decision, I would monitor:

- Day-14 / Day-30 retention
- Revenue per user
- Conversion to purchase
- Average revenue per paying user
- Player progression behaviour
- Engagement / game rounds
- Longer-term retention by player segment

---

# 🧠 Key Takeaway

> **Gate 40 did not produce a statistically significant change in Day-1 retention, but it was associated with a statistically significant decline in Day-7 retention. Based on retention alone, Gate 40 should not be rolled out.**

The key product question is no longer simply *"Is the result statistically significant?"*

It is:

> **"Is the observed retention decline acceptable given the potential product benefits of moving the progression gate?"**

Additional monetization and longer-term retention data would be needed to answer that question confidently.

---

## 🛠️ Tools Used

- Microsoft Excel
- Pivot Tables
- Excel formulas
- Statistical hypothesis testing
- Two-proportion z-test
- Confidence intervals
- Bootstrap simulation
- Data visualization

---

## 📌 Skills Demonstrated

- A/B Testing
- Hypothesis Testing
- Statistical Analysis
- Retention Analysis
- Data Cleaning
- Uncertainty Analysis
- Business Impact Analysis
- Data Visualization
- Product Decision-Making

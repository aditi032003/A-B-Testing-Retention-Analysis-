# 📄 Product Decision Memo

## 🚦 Recommendation: ❌ Do Not Ship Gate 40

Moving the progression gate from **Level 30 to Level 40** reduced retention at both checkpoints:

| Metric | Gate 30 | Gate 40 | Difference | p-value |
|---|---:|---:|---:|---:|
| Day 1 | 44.82% | 44.23% | −0.59 pp | 7.39% |
| Day 7 | 19.02% | 18.20% | −0.82 pp | 0.159% |

**Day 1:** The decline is not statistically significant (p = 7.39%).

**Day 7:** The decline is statistically significant (p = 0.159%), with the 95% confidence interval ranging from **−1.33 to −0.31 pp**.

The bootstrap analysis also shows that the estimated retention gap varies across repeated simulations, helping quantify the uncertainty around the observed effect.

![image alt](https://github.com/aditi032003/A-B-Testing-Retention-Analysis-/blob/d58ae1746af5ade9a62d14ec020e0da8b3cea0f6/Screenshot%202026-10-06%20222658.png)


### Why this matters

At a scale of **1 million players**, the observed Day-7 difference represents approximately **8,183 fewer retained players** under Gate 40.

### Decision

**Keep Gate 30 for now.** Gate 40 provides no retention benefit and shows a statistically significant negative impact by Day 7.

Before revisiting the change, measure **longer-term retention, engagement, and monetization** to understand the full product impact.

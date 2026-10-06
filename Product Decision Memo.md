# 📄 Product Decision Memo

**To:** Product & Growth Team  
**From:** Data Analyst  
**Subject:** Should we move the progression gate from Level 30 to Level 40?  
**Experiment:** Gate 30 vs. Gate 40  
**Sample:** 90,188 players after data cleaning

---

## 🚦 Executive Decision

### **NO-SHIP — Do not roll out Gate 40 based on the current retention evidence.**

Moving the first progression gate from Level 30 to Level 40 resulted in **lower retention at both Day 1 and Day 7**.


### Why this matters

The Day-1 decline was not statistically significant, but the Day-7 decline was statistically significant.

At a scale of 1 million players, the observed differences would represent approximately:

- **5,915 fewer Day-1 retained players**
- **8,183 fewer Day-7 retained players**

The evidence therefore suggests that moving the gate to Level 40 may negatively affect longer-term retention.

---

## 🎮 What Did We Test?

The experiment compared two versions of the game:

| Version | First Progression Gate |
|---|---|
| **Gate 30** | Level 30 |
| **Gate 40** | Level 40 |

The goal was to determine whether delaying the progression gate affected player retention.

### Experiment Size

- **Gate 30:** 44,699 players
- **Gate 40:** 45,489 players
- **Total:** 90,188 players

The two groups were approximately balanced, supporting the basic comparison.

---

## 📊 Key Findings

### Day-1 Retention

| Metric | Gate 30 | Gate 40 | Difference |
|---|---:|---:|---:|
| Retention | **44.82%** | **44.23%** | **−0.59 pp** |

**Statistical result:**

- **p-value:** 7.39%
- **95% CI:** −1.24 pp to +0.06 pp
- **Result:** Not statistically significant at the 5% level

### What this means

We do **not** have enough evidence to conclude that moving the gate to Level 40 changed Day-1 retention.

---

### Day-7 Retention

| Metric | Gate 30 | Gate 40 | Difference |
|---|---:|---:|---:|
| Retention | **19.02%** | **18.20%** | **−0.82 pp** |

**Statistical result:**

- **p-value:** 0.159%
- **95% CI:** −1.33 pp to −0.31 pp
- **Result:** Statistically significant at the 5% level

### What this means

The evidence suggests that moving the gate to Level 40 is associated with a **real decline in Day-7 retention**.

---

## 🔄 Uncertainty Check

I also simulated the experiment **10,000 times** to understand how much the estimated retention gap could vary due to random variation.

The bootstrap analysis provides a visual view of the uncertainty around the observed effects.

![image alt](https://github.com/aditi032003/A-B-Testing-Retention-Analysis-/blob/d58ae1746af5ade9a62d14ec020e0da8b3cea0f6/Screenshot%202026-10-06%20222658.png)


### Why this matters

**Day 1:** The simulated results show greater uncertainty around the observed −0.59 pp difference, consistent with the non-significant p-value.

**Day 7:** The simulated results show a more consistently negative retention gap, supporting the statistically significant Day-7 result.

---

## 💰 Business Impact

Although the percentage-point differences appear relatively small, they become meaningful at scale.

For every **1 million players**, the observed differences represent approximately:

| Retention Metric | Estimated Impact |
|---|---:|
| Day 1 | **5,915 fewer retained players** |
| Day 7 | **8,183 fewer retained players** |

This makes the negative Day-7 effect potentially meaningful from a product perspective.

---

## ⚠️ Risks & What We Still Don't Know

This experiment tells us about retention, but it does **not** tell us:

- Whether Gate 40 affects revenue or monetization
- Whether the effect persists beyond Day 7
- Whether player engagement changes
- Whether the change affects player experience
- Whether the effect changes over a longer period

Retention should therefore not be evaluated in isolation.

---

## 🔎 What I Would Measure Next

Before making a final rollout decision, I would evaluate:

### Longer-Term Retention
- Day-14 retention
- Day-30 retention

### Engagement
- Game rounds per player
- Session frequency
- Session duration
- Progression through the game

### Monetization
- Conversion to payer
- Revenue per user
- Average revenue per paying user
- Purchase frequency

### Player Experience
- Progression difficulty
- Churn points
- Player feedback

---

## 🎯 Recommendation

### **Keep Gate 30 as the safer option for now.**

The evidence is directionally negative at both retention checkpoints, with a statistically significant decline by Day 7.

If the business wants to continue testing Gate 40, I would recommend a further experiment that measures:

**Retention + Engagement + Monetization + Longer-term player behavior**

before making a full rollout decision.

---

## Final Decision

> ### ❌ NO-SHIP: Gate 40

**Primary reason:** Statistically significant negative impact on Day-7 retention.

**Confidence:** High for the Day-7 retention finding; lower for Day 1.

**Next step:** Validate the impact on longer-term retention, engagement, and monetization before making a final product decision.

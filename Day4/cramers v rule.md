from pathlib import Path

content = """# Cramér's V — Strength of Association

## 1. What is Cramér's V?

Cramér's V is used **after a Chi-Square Test of Independence** to measure the **strength of association** between two categorical variables.

The Chi-Square test answers:

> **Is there evidence of an association?**

Cramér's V answers:

> **How strong is that association?**

---

## 2. Formula

$$
V = \\sqrt{\\frac{\\chi^2}{N \\times \\min(r-1,c-1)}}
$$

Where:

- $\\chi^2$ = Chi-Square statistic
- $N$ = total sample size
- $r$ = number of rows
- $c$ = number of columns

---

## 3. Range

$$
0 \\leq V \\leq 1
$$

- $V=0$ → no association
- $V$ close to 1 → very strong association

Cramér's V does **not** indicate the direction of the relationship.

---

## 4. Rule of Thumb for Interpretation

| Cramér's V | Interpretation |
|---:|---|
| 0 | No association |
| 0–0.10 | Very weak |
| 0.10–0.20 | Weak |
| 0.20–0.40 | Moderate |
| 0.40–0.60 | Strong |
| 0.60–0.80 | Very strong |
| 0.80–1.00 | Extremely strong |

> **Important:** These are rules of thumb, not universal statistical laws. The appropriate interpretation can depend on the field, table dimensions, and context.

---

## 5. Example

Suppose:

$$
\\chi^2 = 16.67
$$

$$
N = 100
$$

and the contingency table is $2 \\times 2$.

Therefore:

$$
\\min(r-1,c-1)
=
\\min(2-1,2-1)
=
1
$$

Now:

$$
V =
\\sqrt{\\frac{16.67}{100(1)}}
$$

$$
V = \\sqrt{0.1667}
$$

$$
\\boxed{V \\approx 0.408}
$$

### Interpretation

A Cramér's V of approximately **0.408** indicates a **relatively strong association** according to the rule of thumb above.

---

## 6. Chi-Square vs Cramér's V

| Measure | Main Question |
|---|---|
| Chi-Square test | Is there evidence of an association? |
| p-value | Is the association statistically significant? |
| Cramér's V | How strong is the association? |
| Residuals | Which cells deviate from independence, and in which direction? |

### Remember

$$
\\boxed{\\text{Chi-Square} \\rightarrow \\text{Significance}}
$$

$$
\\boxed{\\text{Cramér's V} \\rightarrow \\text{Strength}}
$$

$$
\\boxed{\\text{Residuals} \\rightarrow \\text{Cell-level direction/deviation}}
$$

---

## 7. Complete Data Analyst Interpretation

A good Data Analyst interpretation combines the test and effect size.

For example:

> The Chi-Square Test of Independence indicates a statistically significant association between the two categorical variables ($p < 0.05$). Cramér's V is approximately 0.41, indicating a relatively strong association based on the chosen rule of thumb.

Do **not** say:

> Gender causes purchasing.

Instead say:

> Gender and purchasing behavior are statistically associated in this dataset.

Remember:

$$
\\boxed{\\text{Association} \\neq \\text{Causation}}
$$

---

## 8. Important Point About Direction

Cramér's V ranges from 0 to 1, so it does **not** tell you whether an association is positive or negative.

For cell-level interpretation, use Pearson residuals:

$$
R_{ij} =
\\frac{O_{ij}-E_{ij}}{\\sqrt{E_{ij}}}
$$

- $R>0$ → observed frequency is greater than expected
- $R<0$ → observed frequency is less than expected
- $R\\approx0$ → observed frequency is close to expected

Therefore:

> **Cramér's V tells you strength; residuals help explain the direction of individual cell deviations.**

---

# Quick Revision

### Formula

$$
\\boxed{
V = \\sqrt{\\frac{\\chi^2}{N \\times \\min(r-1,c-1)}}
}
$$

### Range

$$
\\boxed{0 \\leq V \\leq 1}
$$

### Mental Model

```text
Two categorical variables
        ↓
Chi-Square Test
        ↓
Is there evidence of association?
        ↓
Cramér's V
        ↓
How strong is the association?
        ↓
Residual Analysis
        ↓
Which cells drive the association?

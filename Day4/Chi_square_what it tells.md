# Chi-Square Test of Independence

## Data Analyst Perspective

This project/study explains the **Chi-Square Test of Independence** from a Data Analyst perspective.

The main objective is to understand whether there is an **association between two categorical variables**, how the test is calculated, and how the result can be visualized using **Observed vs Expected frequencies, Chi-Square contributions, residuals, residual heatmaps, and sieve plots**.

---

## 1. What is the Chi-Square Test?

The Chi-Square Test of Independence is used to determine whether two categorical variables are **independent** or whether there is evidence of an **association** between them.

### Example

Suppose we have:

**Gender × Admission Status**

| Gender | Yes | No | Total |
|---|---:|---:|---:|
| Male | 30 | 20 | 50 |
| Female | 10 | 40 | 50 |
| **Total** | **40** | **60** | **100** |

The question is:

> **Is Admission Status associated with Gender?**

---

# 2. Independent vs Dependent / Associated

## Independent

Two categorical variables are independent when there is no evidence of an association between them.

For example:

> Gender and Admission Status are independent.

This means the admission pattern does not show a systematic relationship with gender.

### Null Hypothesis

\[
H_0: \text{The two variables are independent}
\]

---

## Dependent / Associated

If the observed pattern differs sufficiently from what would be expected under independence, we have evidence of an association.

### Alternative Hypothesis

\[
H_1: \text{The two variables are dependent}
\]

In Data Analyst language, it is generally better to say:

> **There is evidence of an association between the variables.**

rather than simply saying:

> "The variables are dependent."

---

# 3. Core Idea

The entire Chi-Square test can be understood through:

```text
Observed Frequencies
        ↓
Expected Frequencies
        ↓
Compare O vs E
        ↓
Chi-Square Contributions
        ↓
Total χ²
        ↓
Statistical Decision
        ↓
Residual Analysis
        ↓
Visualization
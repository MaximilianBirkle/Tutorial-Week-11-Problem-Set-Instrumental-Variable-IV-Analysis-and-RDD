# 🧩 Tutorial-Week-11-Problem-Set-Instrumental-Variable-IV-Analysis-and-RDD

For this assignment, read the **Acemoglu, Johnson, and Robinson (2001)** article:

**Acemoglu, D., Johnson, S., & Robinson, J. A. (2001).** The Colonial Origins of Comparative Development: An Empirical Investigation. *American Economic Review*, *91*(5), 1369–1401.

You will find in the Google drive a file named **`maketable5.dta`** that contains the replication dataset.

Use the following controls throughout:

`f_french`, `f_brit`, `sjlofr`, `catho80`, `muslim80`, `no_cpm80`, `lat_abst`.

You may complete the assignment in **R** (e.g., using `AER::ivreg`) or **Python** (e.g., using `linearmodels.iv`).

---

## Q1. Writing and Estimating the IV Model (10 pts)

1. **Write down the two-equation IV system** (first stage and second stage).
    
    Define explicitly:
    
    - $Y_i$: outcome
    - $T_i$: endogenous regressor
    - $Z_i$: instrument
    - $X_i$: controls
2. Estimate the following:
    - **First stage:**
        
        $T_i = \alpha_1 + \beta_1 Z_i + \mathbf{X}_i' \gamma_1 + \varepsilon_{1i}$
        
    - **Reduced form:**
        
        $Y_i = \alpha_2 + \delta_1 Z_i + \mathbf{X}_i' \gamma_2 + \varepsilon_{2i}$
        
    - **2SLS:**
        
        $Y_i = \alpha_3 + \beta_2 T_i + \mathbf{X}_i' \gamma_3 + \varepsilon_{3i}$
        
3. Report and interpret:
    - The reduced-form coefficient on $Z_i$.
    - The first-stage coefficient on $Z_i$.
    - The **first-stage F-statistic**. Is it above the rule-of-thumb threshold of ≈10?
    - The 2SLS estimate of the effect of $T_i$ on $Y_i$. Is it statistically significant?

---

## Q2. Randomization and Resampling (10 pts)

### Q2(a). Permutation Test

1. **State the null hypothesis** being tested.
2. Conduct a **permutation test** for the IV coefficient:
    - Shuffle the endogenous variable (or fitted values) while holding other variables fixed.
    - Re-estimate the IV model for each permutation.
    - Construct the empirical null distribution.
    - Report the **permutation p-value**.
3. Compare this p-value to the **normal-approximation p-value** from your 2SLS output.
    
    Discuss any differences and what they imply for small-sample IV inference.
    

---

### Q2(b). Bootstrap Confidence Intervals

Using bootstrap resampling of observations:

1. Generate bootstrap 2SLS estimates of the coefficient on TiT_iTi.
2. Construct three 95% confidence intervals:
    - **Efron percentile**
    - **Bias-corrected (BC—google this one.)**
3. Compare the three CIs:
    - Do they include zero?
    - Are they wider or narrower?
    - What does this imply about the sampling distribution?

---

### Q2(c). Conceptual: Permutation vs Bootstrap

Explain—precisely—what the **permutation test** and the **bootstrap** each measure.

What is held fixed? What is resampled?

Why do they answer conceptually different questions?

---

## Q3. Instrument Validity and Timing (10 pts)

1. Explain why settler mortality must be **causally prior** to institutions in AJR’s theory.
2. Why does the **timing of the settler mortality measurements** (often recorded long after colonization) create problems for:
    - **Relevance**
    - **Exclusion restriction**
    - **Independence**
3. Do you find the AJR results convincing? Answer with reference to the IV assumptions and the estimated strength of the first stage.

---

# **Q4. Albouy’s Critique of AJR (10 pts)**

Please read

**Albouy, D. (2012).** The Colonial Origins of Comparative Development: An Investigation of the Settler Mortality Data. *American Economic Review*, *102*(6), 3059–3076.

 Answer the following:

### Q4(a). Measurement Problems

Albouy argues that the settler mortality data are measured with severe error.

Identify at least two of the key measurement issues he raises, and explain why they matter for IV validity.

---

### Q4(b). Violations of IV Assumptions

For each IV assumption—**relevance**, **independence**, and **exclusion restriction**—summarize Albouy’s argument for why the AJR instrument may violate that assumption.

---

### Q4(c). Sensitivity and Data Corrections

Albouy reconstructs and corrects the mortality data.

What happens to:

- the first stage?
- the reduced form?
- the 2SLS estimates?

What do these results reveal about the stability of the AJR findings?

---

### Q4(d). Interpretation

Based on the Albouy critique and your replication results:

- Do you believe the AJR conclusions still hold?
- Or do the methodological issues undermine the core causal claim?
    
    Justify your answer clearly and precisely.
    

## Regression Discontinuity

# **Problem 2 — Regression Discontinuity (RD) Design**

This question is optional. I just want you to have seen this form of analysis, and an example that you can come back to.  Please read:

**Klašnja, M. & Titiunik, R. (2017). *“The Incumbency Curse: Weak Parties, Term Limits, and Unfulfilled Accountability.”* American Political Science Review.**

---

## **Part A — Theory and Identification**

**Q1.** 

Briefly describe:

1. The political theory Klašnja & Titiunik (2017) seek to test. What is the *incumbency curse* and why might it arise in weak-party, term-limited systems?
2. The identification strategy.
    
    Explain how a regression discontinuity design is used to estimate the causal effect of incumbency.
    
3. The assumptions required for the RD design to be valid.
    - State each assumption *formally* (using potential outcomes).
    - Then interpret each assumption in terms of the political process.
4. Give at least two concrete scenarios in which these assumptions might be violated.

---

## **Part B — Replicating Descriptive Statistics and Main RD Results**

Download the dataset `KlasnjaTitiunik-Brazil-data.dta`.

**Q2.** 

1. Report descriptive statistics for the Brazilian municipalities and replicate **Table 1** of the paper.
2. Replicate the paper’s **main RD estimates** (Table 2).
3. Replicate **Figure 1**: the RD plot for vote margin at time ttt and victory at time t+1t+1t+1.
4. Interpret the results: What do the RD estimates imply about the incumbency curse?

---

## **Part C — McCrary Test for Sorting**

**Q3.** 

The validity of the RD design requires no manipulation of vote margins around the cutoff.

1. Explain the idea behind the **McCrary density test**.
    
    What is being tested? Why is this important for RD?
    
2. Implement the McCrary test for sorting at the cutoff using the running variable in this study.
    
    Produce the McCrary density plot and state the estimated discontinuity.
    
3. Interpret the plot and the test statistic.
    
    Is there evidence of sorting or manipulation around the cutoff?
    

---

## **Part D — Assumptions, Threats, and Interpretation**

**Q4.**

Connect the results to broader issues about RD validity in elections:

1. Give two real-world political processes in Brazilian municipal elections that could violate the RD assumption of continuity in potential outcomes.
2. Discuss whether the empirical evidence from Q3 (density test) supports or undermines the credibility of the RD design in this context.

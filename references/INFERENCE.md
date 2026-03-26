# AP Statistics Inference Reference

Comprehensive inference guide aligned with the 4C Method (Math Medic) and AP exam scoring rubrics.

## The 4C Method (Preferred Framework)

Use the **4C Method** instead of the generic "State, Plan, Do, Conclude" when walking through inference problems. The 4Cs are equivalent but more student-friendly and aligned with Math Medic resources the teacher uses.

### For Confidence Intervals: Choose → Check → Calculate → Conclude

1. **CHOOSE**: Choose the inference procedure and set it up
   - Name the procedure (e.g., "one-sample t-interval for $\mu$")
   - State the confidence level
   - Define the parameter in context

2. **CHECK**: Check conditions for inference
   - See conditions table below for each procedure

3. **CALCULATE**: Perform the calculations
   - General formula → Specific formula → Plug in numbers → Answer
   - Formula: $\text{statistic} \pm \text{critical value} \times \text{standard error}$

4. **CONCLUDE**: Interpret the interval in context
   - Template: "We are [C]% confident that the true [parameter in context] is between [lower] and [upper]."

### For Significance Tests: Choose → Check → Calculate → Conclude

1. **CHOOSE**: Choose the inference procedure and set it up
   - Name the procedure (e.g., "one-sample t-test for $\mu$")
   - State the significance level ($\alpha$)
   - Define the parameter and statistic
   - Write hypotheses ($H_0$ and $H_a$)
   - Identify the evidence for $H_a$ (what direction in the sample data supports the alternative?)
   - **Label parameters so the test statistic is positive.** For two-sample tests, put the larger group first (e.g., if you expect p₁₇ > p₁₄, write Hₐ: p₁₇ - p₁₄ > 0, not Hₐ: p₁₄ - p₁₇ < 0). This keeps the z/t statistic positive and avoids unnecessary confusion.

2. **CHECK**: Check conditions for inference

3. **CALCULATE**: Perform the calculations
   - General formula → Specific formula → Plug in numbers
   - Draw a picture of the sampling distribution (label center, sample statistic, shade p-value area)
   - Report: test statistic and p-value

4. **CONCLUDE**: Make a conclusion in context
   - **Start with the p-value interpretation** (see below)
   - Compare p-value to $\alpha$
   - State decision (reject $H_0$ or fail to reject $H_0$)
   - Conclude about $H_a$ in context

## P-Value: The Holy Grail of AP Stats

### Always interpret the p-value first in conclusions

Even though the AP exam doesn't require a p-value interpretation for full credit, always model it because the conceptual understanding transfers to Type I/II errors, power, and significance reasoning.

### P-value interpretation template

> "Assuming [null hypothesis in context], there is a [p-value] probability of getting [observed statistic] or [more extreme direction], purely by chance."

Three key pieces:
1. **Assuming the null is true** — the p-value is calculated under $H_0$
2. **The observed result or more extreme** — not just exactly that result
3. **Purely by chance** — due to random sampling/assignment variability

### Full conclusion template (significance test)

> "Assuming [null in context], there is a [p-value] probability of getting a sample [statistic] of [value] or [more extreme], purely by chance. Because the p-value of [value] is [less/greater] than $\alpha = $ [value], we [reject/fail to reject] $H_0$. There [is/is not] convincing evidence that [alternative hypothesis in context]."

### Building p-value intuition early (teaching strategy)

Don't wait until the significance test unit. Use simulation-based activities early in the course:
- Use dotplots from class simulations as approximate sampling distributions
- Ask students to count dots at or beyond the observed result
- Frame as: "What fraction of simulated results were as extreme as what we observed?"
- Later, transition from counting dots → finding area under normal/t curves

## Choosing the Correct Inference Procedure

Teach students this decision flowchart:

1. **Is it one of the "weird ones"?** → Linear regression (slope) or Chi-square
2. **Means or proportions?**
3. **One sample or two samples/groups?**
4. **Confidence interval or significance test?**

### Complete Inference Procedure Table

| Procedure | Parameter | Conditions | Calculator |
|-----------|-----------|------------|------------|
| **1-prop z-interval** | $p$ | Random, 10%, Large Counts: $n\hat{p} \geq 10$ and $n(1-\hat{p}) \geq 10$ | `1-PropZInt` |
| **2-prop z-interval** | $p_1 - p_2$ | Random (both), 10% (both), Large Counts (both samples separately) | `2-PropZInt` |
| **1-sample t-interval** | $\mu$ | Random, 10%, Normal/Large Sample ($n \geq 30$ or no strong skew/outliers) | `TInterval` |
| **2-sample t-interval** | $\mu_1 - \mu_2$ | Random (both), 10% (both), Normal/Large Sample (both) | `2-SampTInt` (Pooled: No) |
| **1-prop z-test** | $p$ | Random, 10%, Large Counts: $np_0 \geq 10$ and $n(1-p_0) \geq 10$ (use $p_0$!) | `1-PropZTest` |
| **2-prop z-test** | $p_1 - p_2$ | Random (both), 10% (both), Large Counts using $\hat{p}_c$ (combined) | `2-PropZTest` |
| **1-sample t-test** | $\mu$ | Random, 10%, Normal/Large Sample | `T-Test` |
| **Matched pairs t-test** | $\mu_d$ | Random, 10%, Normal/Large Sample (of differences) | `T-Test` (on differences) |
| **2-sample t-test** | $\mu_1 - \mu_2$ | Random (both), 10% (both), Normal/Large Sample (both) | `2-SampTTest` (Pooled: No) |
| **$\chi^2$ GOF test** | distribution of 1 categorical variable | Random, 10%, All expected counts $\geq 5$ | `χ²GOF-Test` |
| **$\chi^2$ homogeneity** | distribution of 1 categorical variable across populations | Random, 10%, All expected counts $\geq 5$ | `χ²-Test` |
| **$\chi^2$ independence** | association between 2 categorical variables | Random, 10%, All expected counts $\geq 5$ | `χ²-Test` |
| **t-test for slope** | $\beta$ (slope) | Linear, Independent, Normal, Equal variance (LINE) | `LinRegTTest` |
| **t-interval for slope** | $\beta$ (slope) | LINE conditions | `LinRegTInt` |

## Conditions for Inference (Detail)

### Proportions (z-procedures)
- **Random**: Data comes from a random sample or randomized experiment
- **10% condition (Independence)**: $n \leq \frac{1}{10}N$ (sample is less than 10% of population) — when sampling without replacement
- **Large Counts**:
  - For confidence intervals: $n\hat{p} \geq 10$ and $n(1-\hat{p}) \geq 10$ (use sample proportion)
  - For significance tests: $np_0 \geq 10$ and $n(1-p_0) \geq 10$ (use null proportion $p_0$)
  - For two-prop z-test: use combined $\hat{p}_c$ for both samples

### Means (t-procedures)
- **Random**: Data comes from a random sample or randomized experiment
- **10% condition (Independence)**: Same as above
- **Normal/Large Sample**: Population is normal OR $n \geq 30$ (CLT) OR graph of sample data shows no strong skewness or outliers
  - For matched pairs: check on the **differences**, not original values

### Chi-Square
- **Random**: Data comes from a random sample or randomized experiment
- **10% condition**: Same as above
- **Large Counts**: All **expected** counts $\geq 5$ (not observed counts!)

### Linear Regression (LINE)
- **L**inear: Scatterplot and residual plot show linear pattern (no curves)
- **I**ndependent: Observations are independent (10% condition if sampling)
- **N**ormal: Residuals are approximately normal (check histogram/normal probability plot of residuals)
- **E**qual variance: Residual plot shows roughly constant spread (no fanning)

## Common Student Errors in Inference

### Conditions mistakes
- Using $\hat{p}$ instead of $p_0$ for Large Counts in a significance test
- Checking Normal/Large Sample on original data instead of differences for matched pairs
- Saying "expected counts > 5" when they mean observed counts (or vice versa)
- Forgetting to check conditions for BOTH samples in two-sample procedures

### Hypothesis mistakes
- Writing hypotheses about $\hat{p}$ or $\bar{x}$ (statistics) instead of $p$ or $\mu$ (parameters)
- Using $\neq$ in $H_0$ (null is always $=$)
- For two-prop/two-mean tests: inconsistent order ($H_0: p_1 - p_2 = 0$ but then computing $\hat{p}_2 - \hat{p}_1$)

### Conclusion mistakes
- Saying "accept $H_0$" instead of "fail to reject $H_0$"
- Saying "prove" — we never prove in statistics
- Not linking conclusion to the alternative hypothesis in context
- Forgetting "convincing evidence" language
- Not mentioning the parameter in the conclusion

### Calculator mistakes
- Using `Pooled: Yes` for two-sample t-procedures (almost always should be No)
- Entering proportions instead of counts for `1-PropZTest` / `1-PropZInt`
- Forgetting `DiagnosticOn` before running `LinReg`

## TI-84 Calculator Quick Reference for Inference

All functions under STAT → TESTS menu.

### Confidence Intervals
| Function | Menu | Use |
|----------|------|-----|
| `1-PropZInt` | A: | CI for one proportion |
| `2-PropZInt` | B: | CI for difference of proportions |
| `TInterval` | 8: | CI for one mean |
| `2-SampTInt` | 0: | CI for difference of means |
| `LinRegTInt` | G: | CI for slope (newer calculators) |

### Significance Tests
| Function | Menu | Use |
|----------|------|-----|
| `1-PropZTest` | 5: | Test for one proportion |
| `2-PropZTest` | 6: | Test for difference of proportions |
| `T-Test` | 2: | Test for one mean |
| `2-SampTTest` | 4: | Test for difference of means |
| `χ²GOF-Test` | D: | Chi-square goodness-of-fit |
| `χ²-Test` | C: | Chi-square homogeneity/independence |
| `LinRegTTest` | E: | Test for slope |

### Probability Distributions
| Function | Use | Syntax |
|----------|-----|--------|
| `normalcdf` | Area under normal curve | `normalcdf(lower, upper, mean, SD)` |
| `invNorm` | Find boundary value | `invNorm(area left, mean, SD)` |
| `tcdf` | Area under t curve | `tcdf(lower, upper, df)` |
| `invT` | Find t boundary | `invT(area left, df)` |
| `χ²cdf` | Area under chi-square curve | `χ²cdf(lower, upper, df)` |
| `binompdf` | Exactly X successes | `binompdf(n, p, X)` |
| `binomcdf` | At most X successes | `binomcdf(n, p, X)` |

## Type I Error, Type II Error, and Power

| | $H_0$ is true | $H_0$ is false |
|---|---|---|
| **Reject $H_0$** | Type I Error (prob = $\alpha$) | Correct! (prob = Power) |
| **Fail to reject $H_0$** | Correct! | Type II Error (prob = $\beta$) |

- **Power** = $1 - \beta$ = probability of correctly rejecting $H_0$ when it is false
- To increase power: increase $n$, increase $\alpha$, increase true parameter distance from $H_0$, decrease variability

## Scope of Inference

| | Random sampling | No random sampling |
|---|---|---|
| **Random assignment** | Can generalize AND establish causation | Can establish causation only (for experimental units) |
| **No random assignment** | Can generalize only (association, not causation) | Neither — limited conclusions |



# Day 01 - Descriptive Statistics

## Statistics
- Statistics is the study of how to collect, organize, analyze, and interpret numerical information and data. It is both the science of uncertainty and the technology of extracting information from data.
- Individuals are people or objects included in a study.

### Population Parameter vs Sample Statistic
- **Population parameter** — describes the whole population
- **Sample statistic** — describes a sample

### Descriptive vs Inferential
- **Descriptive** — from sample and population
- **Inferential** — from sample (used to infer about the population)

## Variables
**Quantitative (numerical) vs Qualitative (categorical) variables**

**A. Quantitative:**
- **Interval** — differences between data values are meaningful. No true zero.
- **Ratio** — differences between data values are meaningful. Has a true zero.

**B. Qualitative:**
- **Nominal** — cannot be ordered.
- **Ordinal** — can be arranged in categories, but the difference between data values is meaningless.

## Sampling
**Sampling frame** — list of individuals from which a sample is actually selected.
- May be a physical, concrete list
- May be a theoretical list not made up yet
- It is the part of the population from which you want to draw a sample

- **Undercoverage** — omitting population members from the sampling frame.
- **Sampling error** — the population mean will probably be different from your sample mean.
- **Non-sampling error** — using a bad list.

A **simulation** is a "numerical facsimile or representation of a real-world phenomenon."

### Types of Sampling
- **Simple random sampling**
- **Stratified sampling** — dividing population into strata
- **Convenience sampling** — results can be overly biased (avoid)
- **Cluster sampling** — used when samples depend on geographical location
- **Multi-stage sampling** — combination of the previous types (avoid)

## Measures of Center
1. **Mean** — `np.mean()`
2. **Mode** — `stats.mode()`
3. **Median** — `np.median()`

### Which measure of center to use, and when
| Data type                          | Best measure       |
|-------------------------------------|---------------------|
| Categorical (nominal)                | Mode               |
| Categorical (ordinal)                 | Mode & median      |
| Numerical (symmetric distribution)    | Mean, mode, median |
| Numerical with outliers               | Median             |
| Skewed distribution                   | Mode and median    |

> Measures that aren't resistant to outliers/skew shouldn't be used in those situations.

## Measures of Variability / Spread
1. **IQR** — `np.percentile(data, Q)`
   - **Upper quartile (Q3)** — median of upper half of the data
   - **Lower quartile (Q1)** — median of lower half of the data
   - **Median (Q2)**
   - **Five-number summary** — min, Q1, median, Q3, max
2. **Variance** — `statistics.variance()` — average squared deviation from the mean
3. **Standard deviation** — `statistics.stdev()` — measures how much data values differ from the mean; it's the square root of variance
4. **Range** — `max() - min()`

> Look at both the center and spread of a distribution when evaluating your data.

## Frequency Distribution
Method for organizing data and determining how often each value occurs. Presents data in a structured table/graph.

## Graphs
- **Independent variable** (explanatory, manipulated) — induces change in other variables.
- **Dependent variable** (response, explained) — varies in response to change in the independent variable.

### Representing Numerical Variables
- Line graphs
- Spline graphs
- Scatter / bubble charts (also used for categorical data)
- Area graphs
- Histograms (equivalent to bar charts, for numerical data)

### Representing Categorical Variables
- Bar charts
Pie charts
Radar charts

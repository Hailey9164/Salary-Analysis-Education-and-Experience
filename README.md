# Salary Analysis: Education Level and Earnings

## Overview

This project analyzes how **education level impacts salary** using a dataset containing over **53,000 employee records**. The analysis was completed as part of a CS 2410 group project and includes exploratory data analysis (EDA), probability applications, statistical investigations, and visualizations.

The primary research question was:

> How does education level affect salary, and how much of that relationship remains after considering factors such as years of experience?

---

## Team Members

- Hailey Campbell
- Frank Win
- Joseph Yip

---

## Dataset

**Dataset:** `Salary-Data-50k+Records.csv`

The dataset contains information on:

- Salary
- Education Level
- Years of Experience
- Job Title
- Gender
- Age

**Size:** 53,038 records

### Key Variables

| Variable | Type | Role |
|-----------|------|------|
| Salary | Numeric | Outcome Variable |
| Education Level | Categorical | Primary Explanatory Variable |
| Years of Experience | Numeric | Secondary Explanatory Variable |
| Job Title | Categorical | Potential Confounder |
| Gender | Categorical | Exploratory Variable |
| Age | Numeric | Supporting Variable |

---

## Project Goals

The project investigates:

1. The relationship between education level and salary.
2. The impact of work experience on earnings.
3. Whether advanced degrees increase the likelihood of earning higher salaries.
4. How gender relates to salary within the dataset.
5. Whether salary distributions are approximately normal.
6. The viability of the dataset for deeper statistical analysis.

---

## Exploratory Data Analysis (EDA)

### Education Level vs Salary

Education level showed the strongest relationship with salary.

Median salary increased steadily across education categories:

| Education Level | Median Salary |
|---------------|--------------|
| High School | ~$32.6k |
| Bachelor's | ~$79.3k |
| Master's | ~$110.8k |
| PhD | ~$139.9k |

Boxplots were used to visualize salary distributions across education groups.

### Experience vs Salary

Years of experience also showed a strong positive relationship with salary.

Analyses included:

- Scatter plots
- Pearson correlation
- Spearman correlation
- Linear regression
- Grouped salary summaries by experience ranges

### Gender vs Salary

Salary distributions between male and female employees were compared using:

- Boxplots
- Summary statistics
- Mean and median salary gap calculations

### Entry-Level Workers Analysis

To better isolate education effects, workers with:

```python
Years of Experience == 0
```

were analyzed separately.

This provides insight into salary differences among individuals entering the workforce with different educational backgrounds.

---

## Data Quality

### Missing Data

No missing values were found in the key variables used for analysis.

```python
df.isna().sum()
```

### Outlier Detection

Outliers were identified using **Tukey's Fences (1.5 × IQR)**.

```python
Q1 = salary.quantile(0.25)
Q3 = salary.quantile(0.75)
IQR = Q3 - Q1
```

Results showed that removing outliers had minimal impact on median salaries across education groups.

---

## Probability Analysis

The notebook also applies concepts from probability and statistics.

### Example Questions

- Probability that a randomly selected employee earns more than $100,000.
- Probability that at least one employee in a group of five earns over $100,000.
- Testing independence between:
  - High salary
  - Advanced degree attainment
- Bayes' Rule calculations
- Bernoulli and Binomial modeling using the Gender variable
- Normality investigation of salary distributions

### Key Finding

Employees with a Master's degree or PhD were substantially more likely to earn over $100,000 than employees without advanced degrees.

---

## External Data Integration Attempt

An attempt was made to merge the salary dataset with occupation-level wage benchmark data:

```text
national_M2025_dl.xlsx
```

using job titles as matching keys.

The merge produced no exact title matches, highlighting a common real-world data integration challenge involving inconsistent naming conventions.

---

## Main Findings

### Positive Relationship Between Education and Salary

Higher education levels corresponded to substantially higher salaries throughout the dataset.

### Experience Matters

Some salary differences are explained by experience levels, but education continued to show an effect even within comparable experience groups.

### Outliers Do Not Drive Results

Removing high-income outliers produced only small changes in median salaries.

### Salary Is Not Normally Distributed

The salary histogram exhibits multiple peaks and does not follow a clean normal distribution, despite approximately matching the 68-95-99.7 rule.

---

## Limitations

Several potentially important variables were unavailable:

- Location (state/city)
- Employer
- Industry
- Field of study
- Family background
- Hours worked

Because of these missing variables, the results should be interpreted as **associations rather than definitive causal relationships**.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy

---

## Repository Structure

```text
├── Salary_Analysis.ipynb
├── Salary-Data-50k+Records.csv
├── national_M2025_dl.xlsx
├── README.md
```

---

## Future Work

Potential extensions include:

- Occupation-level wage benchmarking
- Multivariate regression analysis
- Industry-specific salary analysis
- Geographic salary comparisons
- Inflation-adjusted earnings analysis
- Improved job-title matching techniques

---

## Conclusion

This analysis provides strong evidence that education level is associated with higher salaries within the dataset. While experience and job title contribute to earnings differences, the relationship between educational attainment and salary remains visible across multiple analyses, making the dataset a useful foundation for further workforce and compensation research.

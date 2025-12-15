# Final-Project-631

# Project Title

## 1. Research Question
This project investigates whether remote workers report higher job satisfaction than onsite workers.
The question matters because remote and hybrid work arrangements now play a major role in the global workforce. Understanding how work mode influences employee well-being can help organizations shape workplace policies, improve retention, and support healthier work environments.

## 2. Hypothesis
* Null Hypothesis (H0): There is no difference in average job satisfaction between remote and onsite workers.
* Alternative Hypothesis (H1): Remote workers report higher job satisfaction than onsite workers.

## 3. Data Description
Data Source:  2025 Stack Overflow Developer Survey
https://survey.stackoverflow.co/ 

Unit of Analysis:
* Each row represents one survey respondent.

Key Variables:
* RemoteWork: Work arrangement category
* JobSat: Job satisfaction score (0–10 scale)
* WorkMode (derived): Simplified classification (remote or onsite)

Sample Size (after cleaning):
* Remote workers: 10,756
* Onsite workers: 3,496

Cleaning Steps:
* Removed responses missing work arrangement or job satisfaction
* Grouped work arrangements into remote and onsite
* Excluded hybrid categories to maintain a clean comparison

## 4. Methods
Permutation Test:
* Test Statistic: Difference in mean job satisfaction (Remote − Onsite)
* Null Simulation: Randomly shuffled work mode labels 5,000 times to generate a null distribution

Bootstrap Confidence Intervals:
* Metric: Median job satisfaction
* The CLT does not apply to median because it is not mean, and its sampling distribution is not guaranteed to be normal.
* Approach: 5,000 bootstrap resamples with replacement using the percentile method

## 5. Results
* Observed mean difference: 0.36 (remote higher than onsite)
* Permutation test p-value: < 0.001
* Bootstrap 95% confidence intervals for median job satisfaction:
    * Remote: [8, 8]
    * Onsite: [7, 7]
* The Histogram and boxplot show that remote workers consistently report higher job satisfaction across the distribution.

## 6. Uncertainty Estimation
Uncertainty was quantified using both permutation testing and bootstrapping. A permutation test with 5,000 random label shuffles produced a null distribution centered near zero, representing differences expected if work mode had no relationship to job satisfaction. The observed mean difference of 0.36 fell far in the right tail of this distribution, resulting in a p-value less than 0.001.

To estimate uncertainty for a non-CLT metric, bootstrap confidence intervals were constructed for the median job satisfaction. Using 5,000 bootstrap resamples, the 95% confidence interval for the median was [8, 8] for remote workers and [7, 7] for onsite workers. Because the median is not a mean, the Central Limit Theorem does not apply, making bootstrapping appropriate. The narrow, non-overlapping intervals indicate a stable and robust difference between groups.

## 7. Limitations
* Job satisfaction is self-reported and may include response bias
* Results are correlational and do not imply causation
* Hybrid workers were excluded to simplify the analysis
* Other factors (pay, role, experience) were not controlled for

## 8. References
* Stack Overflow. 2025 Developer Survey
* Python libraries: Pandas, NumPy, Matplotlib
* SEIS 631 course materials
---
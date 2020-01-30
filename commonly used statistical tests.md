# Intro
This is the summary of commonly used statistical tests.

# Population distribution
## Center

### population mean vs hypothesized
1. If the sample is large, we can use **one sample z test**. The idea
behind is the CLT (central limit theorem), so **no requirements for underlying distribution**.
2. If underlying population is **normal**, we can use **one sample z test** no matter if sample size is large enough, **if the population variance is known**. If not, we use a one sample **t test**.
3. If the underlying distribution is unknown & sample size is not large enough to apply CLT, we use **non-parametric** tests.
a. **bootstrap test for one sample mean**
It includes the following steps:

      Shfit the sample so its mean is $\mu_0$;
      
      Sample with replacement from the shifted sample and caculate the mean;repeat the process several times.
      
      Evaluate how many times the calculated mean is <= (or >=) your actual sample mean.
### two population means comparison
1. **Two idependent large sample mean comparison**: two sample z test; pooled or unpooled variance depending on whether the variances are equal.
2. **Two independent normal population**: **student's t test** or **welch's** t test, depending on whether the two population has the same variance.
3. **Two independent sample with distribution unknown**: **Mann Whitney test**. Notice this test requires the two population to be of **same shape**. 
### population meadian vs hypothesized 
1. **one-sample Sign test**: shift your data so its median is $0$; then test if $p(x > 0)$ is > or < 0.5.
2. **Wilcoxon Signed Rank Test**: you need to have a **symmetric data** to apply this method. 
      
### population mean vs a different population mean
1. if you have paired samples, meaning your two samples are **dependent**, you can obtain the 
difference between each pair, then perform suitable one sample test based on the nature of your data.

2. if you have independent samples, you can choose to run a. **two sample z test** if you have large samples; b. **welch t test** if you cannot assume equal variance and roughly normal samples; c **pooled t test** if you can assume equal variance and roughly normal samples; d. **Mann Whitney U Test (Wilcoxon Rank Sum Test)**, if your samples are not normally distributed, but of same shape. Notice that here you null assumption is that **The two populations are equal**

# Probability distribution tests

## Shapiro -Wilk test (best power if used properly)

## Kolmogorov–Smirnov test (known mean and variance; can also be used for non-normal distrbution tests)

## pearson chi-square test (discrete cases)

# test for r by c table - homogeneity / independence


# Pearson chi-square test usage
For peason chi-square test, the test statistics, in gneneral, is 

$\sum \frac{ (O- E) ^2}{ E^2}$

# Modeling / Regression related




# General
## Likelihood ratio

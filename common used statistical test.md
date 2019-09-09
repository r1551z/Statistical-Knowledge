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
2. **Two independent normal population**: student's t test or welch's t test, depending on whether the two population has the same variance.
3. **Two independent sample with distribution unknown**: **Mann Whitney test**. Notice this test requires the two population to be of **same shape**. 
### population meadian vs hypothesized 
1. **one-sample Sign test**: shift your data so its median is $0$; then test if $p(x > 0)$ is > or < 0.5.
2. **Wilcoxon Signed Rank Test**: you need to have a **symmetric data** to apply this method. 


      
### population mean vs a different population mean

# General
## Likelihood ratio test.

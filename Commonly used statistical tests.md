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
4. **Two dependent population**: paired t-test
### population meadian vs hypothesized 
1. **one-sample Sign test**: shift your data so its median is $0$; then test if $p(x > 0)$ is > or < 0.5.
2. **Wilcoxon Signed Rank Test**: you need to have a **symmetric data** to apply this method. 
      
### population mean vs a different population mean
1. if you have paired samples, meaning your two samples are **dependent**, you can obtain the 
difference between each pair, then perform suitable one sample test based on the nature of your data.

2. if you have independent samples, you can choose to run a. **two sample z test** if you have large samples; b. **welch t test** if you cannot assume equal variance and roughly normal samples; c **pooled t test** if you can assume equal variance and roughly normal samples; d. **Mann Whitney U Test (Wilcoxon Rank Sum Test)**, if your samples are not normally distributed, but of same shape. Notice that here you null assumption is that **The two populations are equal**


## population proportion

### large samples 
z test for population proportion

## small samples
binomial exact test: calculate p-value directly from the binomial distribution under null, without
normal approximation.

two tails: 

a. method 1 is to calculate all p(y) such that abs(y-e(X)) <= abs(x-E(X))

b. method 2 is to sum all p(y), such that p(y)<=p(x), where x is the observed value

# Probability distribution tests

## Shapiro -Wilk test (best power if used properly)

## Kolmogorov–Smirnov test (known mean and variance; can also be used for non-normal distrbution tests)

## pearson chi-square test (discrete cases)
see the section for pearson chi-square test

## run test - test randomness

## sign test - test sample median
statisticshowto.com/one-sample-median-test/

## mood's median test
https://sixsigmastudyguide.com/moods-median-non-parametric-hypothesis-test/
this is actually a pearson chi square test testing if method is related with prob(>pooled median)


# test for r by c table - homogeneity / independence

## large sample
Pearson chi-square test

## small sample
fisher exact test
https://en.wikipedia.org/wiki/Fisher%27s_exact_test

two tails: sum of prob of cases as or more extreme to the observed cases in both 
direction; one method is to deem more extreme as any cases with a lower probability
comparing with current observed case


## wilcoxon singed ranks test

https://en.wikipedia.org/wiki/Wilcoxon_signed-rank_test




# Pearson chi-square test usage

## assumptions

a. random sampling

b. independent obs

c. sample large enough 

## test stats
For peason chi-square test, the test statistics, in gneneral, is 

$\sum \frac{ (O- E) ^2}{ E^2}$

where O being observed freq in a cell / category, and E being the expected one. The difference is that

a. for goodness of fit, we have one way table, with E_i calculated as n * p_i; df will be n - p;

b. for independence and homogeity, we have two way contigency table, with E = p_{\dot j} p_{i \dot} * n

where i, j represents levels of the two ways, p_{\dot j} = \frac{\sum _ i(n_{i, j}}{n},
p_{i \dot} = \frac{\sum _ j(n_{i, j}}{n}; df = (r-1)(c-1), with r and c equal to n of categories
in the rows and columns.




# Modeling / Regression related

## test for single coefficient: t test; 
t = \frac{\hat(\beta)}{se(\hat(beta)}, df=n-p-1

## test for overall relationship.

t = SSR/SSE, F test, df = p, n-p-1

## test for multiple beta 

\frac{(SSE_{reduce} - SSE_{full}) / (p-q)}{SSE_{full}/(n-p-1} ~ F test;

**null hypothesis is reduced model is true**


# General
## Likelihood ratio test

test stat: L = sup_theta(L|H0)/sup_{theta}L(J1) 

rejection region: l < lambda

Neyman-pearson: for simple test H0: theta = theta_0 vs H1: theta = theta1, likelihood ratio test is the most powerful test


Kalin-Rubin theorem: if l = f(theta_1, x)/f(theta_0, x is monotonically non decreasing in x for any pair theta1 > theta0, then phi(x) = I(x>x0) would be is the ump test for H): theta<=theta_0 vs theta> theta_0

importance case:  exponential family g(theta)h(x)exp(eta(theta)T(x)) is has mono-non-decreasing in sufficient stat T, thus mp test is T> t



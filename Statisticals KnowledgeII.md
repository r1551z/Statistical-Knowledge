# Power and sample size calculation

"Sample size estimation and power analysis for clinical
research studies"

##  regular z test calculation:

two sample equal design: n = 2(z_{1-alpha/2} + z_{1-beta})^2 (sigma^2 + sigma^2)/d^2;
with d the difference between two sample mean / two stats to be tested.

two sample unequal design:

https://personalpages.manchester.ac.uk/staff/chris.roberts/MATH38071/Sample%20Size.pdf

>?the required sample size thus increased by (k-1)^2/4k; or inflated by (k+1)^2/4k

say n1/n2=r, result will be (r+1)/2r * n as in equal size design

## for odds ratio


n = (1+r)^2 (z_{1-alpha/2} + z_{1-beta})^2/(r * lg(OR)^2) *p(1-p); with p=prevalence of
exposure in the general population (P); or is served as the d.


another formula can be found here:

https://www2.ccrb.cuhk.edu.hk/stat/proportion/Casagrande.htm


##  for logsitic regression:

https://www.researchgate.net/publication/13586507_A_Simple_Method_of_Sample_Size_Calculation_for_Linear_and_Logistic_Regression



## for anova / mixed effect models

your effect size is then used as the mean between the highest and lowest groups.



##  regression


# sampling method


1. randomized sampling

2. stratified sampling


3. reservior sampling

  used if total number of item in a population is not known or too large to be sampled at once
  
  procedure (sample k out of N):
  ```
  round N: 
  get a random number from 1 to N; drop the Nth dp if the x>k; other wise use the Nth dp to replace the current x^th one 
  ```

4. respondent driven sampling
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4074320/#Sec2title

Method of Variance Estimates Recovery (MOVER): 

# sequential test


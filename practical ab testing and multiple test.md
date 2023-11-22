# Multiple test

reference:
1. Correcting for multiple-testing in multi-arm trials: is it necessary and is it done? https://trialsjournal.biomedcentral.com/articles/10.1186/1745-6215-15-364
2. What is the proper way to apply the multiple comparison test? https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6193594/#:~:text=When%20used%20as%20a%20post,the%20very%20conservative%20Scheff%C3%A9's%20method.
3. Step-down procedures for multiple comparisons (http://new.pmean.com/step-down-procedures/)
4. Dunnett's test (https://en.wikipedia.org/wiki/Dunnett%27s_test)
5. Non-adjustment for multiple testing in multi-arm trials of distinct treatments: Rationale and justification (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7534018/）
6. 
## what are they? what are the potential issues? 

In real life, one thing we usually encounter is the multi-arm experiement, in which wee test multiple treatment agains
the control group. The hypothesis tested can be

1. mu0 = mu1 vs mu0!= mu1.
2. mu0 = mu2 vs mu0!= mu2.
...
k.  mu0 = mu_k vs mu0!= mu_k.

while we are testing for the effectiveness of the test, we can encounter with the issue of 
inflated type I error.

### how is the issue possible？
It is because your type I error here is defined as the probabity that 
you falsely reject any of test
P(reject while mu0=mu1 or reject while mu0=mu2...)
if for each test the type I error is alpha, and if we have independent tests, then
our overall type I error could be 

1 - (1-alpha)^k

### the corrections

#### Bonferroni
with tylar expansion, this value is approximately equal to 1 - (f(0)+f'(0)*alpha) 
with f(x) = (1-x)^k, thus the value is 1 - (1 + k(-1) * alpha) = k * alpha

Thus leads to the bonferoni correction - if we want to control the overall type I error, 
we should use alpha ' = alpha/k for each test.

This is also known for control for the **family-wise error rate (FWER)**
As it's often the case that the tests are not completely independent, the bonerroni correction is usually very conservative.

#### dunnetts method
this is a method that's suitable for one common control group vs multiple treatment group. 

#### Benjamini-Hochberg adjustment 
another method is instead of controlling for the fmer (prob of making type one error in any
of the test, we can also choose to control for false discovery rate, which is the expected proportion of true null-hypotheses that are rejected
among all rejections. 

This method rank all p value from small to large; then compare each with its bejamin hochberg value,
(rank of p/total number of test)*desired FDR. The largest P value for which P < (i / m)∙Q is significant, 
and all the P values smaller than the largest value are also significant, 
even the ones that are not less than their Benjamini-Hochberg critical value.

## should we always perform the corrections?

It has been however arguable if we should always apply the correction to our experiment analysis. Some ppl believe that
it is more relavent if we are testing different doses of the same treatment, or if we are looking into multiple outcome of
the same pairwise comparison, because in this case, any result being wrongly significant will lead to us accepting the treatment.
On the other hand, if we are performing explorary experiments and will have followup confirmatory experiment, the adjustment is
not that necessary. Also, if we are testing multple treatment against the same common treatment group, we have a reason to
view those as independent trails, thus do not need the correction.


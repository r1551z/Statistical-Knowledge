
# Intro
Survival analysis related knowledge.

## Survival function, hazard function and density function

In this section we will have a brief introduction, about distribution related
functions for survival analysis.

### Definition
In survival analysis, we view survival time T as a random variable, and we use
the following four functions to describe it.

cumulative distribution function: $$F(t) = P(T < t)$$

probability density function: $$f(t) = \frac{d{F(t)}}{dt}$$

survival function: $$S(t) = 1 - F(t)$$

hazard function: $$h(t) =-\frac{\frac{dS(t)}{dt}}{S(t)}$$

cumulative hazard function: $$H(t) =\int^t_0 h(x)dx$$

### Relationship
$$h(t) = \frac{f(t)}{S(t)}$$

$$h(t) = -\frac{dlog(S(t))}{dt}$$

$$S(t) = exp(-H(t))$$


## Survival likelihood function
We use $$D$$ to denote the cohort of objects that experienced the event (uncensored) and $$D^c$$ denote the cohort of objects that did not experience the event (censored). We have the likelihood function is:

$$L(t) = \prod_{i \in D}f(t_i)\prod_{i \in D^c}S(t_i)=\prod_iS(t_i) \prod_{i \in D}h(t_i) =\prod_ie^{-H(t_i)} \prod_{i \in D}h(t_i)$$



## Commonly used survival models
### AFT (accelerated failure time model)
#### Basic idea:

$$S_1(t) = S_0(\lambda t)$$

#### A more general form:

$$lnT = x\beta + \epsilon$$

$$\epsilon$$ is a random variable. The commonly used distribution for it includes Weibull and exponential.

#### Prove that the genral form satisfies the basic idea:
$$S(t) = P(T>t) = P(e^{x\beta}e^{\epsilon}>t) = p(Z>\frac{t}{e^{x\beta}}) = S_Z(\frac{t}{e^{x\beta}})$$

$$Z = e^{\epsilon}$$

Therefore 
$$S_1(t) = S_Z(\frac{t}{e^{x_1\beta}}) = S_Z(\frac{t}{e^{x_0\beta}}\frac{e^{x_0\beta}}{e^{x_1\beta}})=S_0(\lambda t)$$

#### likelihood function
##### lemma:
Consider $$X$$ has pdf $$f_X(x, \theta)$$. To estimate $$\hat{\theta}_{MLE}$$ using $$f_X(x, \theta)$$ and a sample $$x_1, x_2, ..., x_n$$ is the same as using $$z_1,...z_n$$ and $$f_Z(z, \theta)$$, with $$Z = g(X)$$.

##### proof:

$$L(x, \theta) = \prod f_X(x_i, \theta)$$

$$L(z, \theta) = \prod f_Z(z_i,\theta)
= \prod \frac{dg^{-1}(z_i)}{dz_i}f_X(g^{-1}(z_i), \theta) \sim \prod f_X(g^{-1}(z_i), \theta) = \prod f_X(x_i, \theta)$$

Similarly, we have 
$$S_Z(z) = P(Z>z) = P(g(X) > g(x)) = p(X>x) = S(x)$$ 

##### likelihood:

From the above lemma we have the following survival full likelihood function, 
$$L(t) = \prod_{i \in D}f_T(t_i)\prod_{i \in D^c}S_T(t_i) \sim \prod_{i \in D}f_{lnT}(ln(t_i))\prod_{i \in D^c}S_{lnT}(ln(t_i))$$

PH (proportional hazard)

Basic idea:

$$h_1(t) = \lambda h_0(t)$$

$$lnT = x\beta + \epsilon$$

$$\epsilon$$ is a random variable. The commonly used distribution for it includes Weibull and exponential.

Prove that the genral form satisfies the basic idea:
$$S(t) = P(T>t) = P(e^{x\beta}e^{\epsilon}>t) = p(Z>\frac{t}{e^{x\beta}}) = S_Z(\frac{t}{e^{x\beta}})$$

$$Z = e^{\epsilon}$$

Therefore 
$$S_1(t) = S_Z(\frac{t}{e^{x_1\beta}}) = S_Z(\frac{t}{e^{x_0\beta}}\frac{e^{x_0\beta}}{e^{x_1\beta}})=S_0(\lambda t)$$


#### likelihood function
##### lemma:
Consider $$X$$ has pdf $$f_X(x, \theta)$$. To estimate $$\hat{\theta}_{MLE}$$ using $$f_X(x, \theta)$$ and a sample $$x_1, x_2, ..., x_n$$ is the same as using $$z_1,...z_n$$ and $$f_Z(z, \theta)$$, with $$Z = g(X)$$.

##### proof:

$$L(x, \theta) = \prod f_X(x_i, \theta)$$

$$L(z, \theta) = \prod f_Z(z_i,\theta)
= \prod \frac{dg^{-1}(z_i)}{dz_i}f_X(g^{-1}(z_i), \theta) \sim \prod f_X(g^{-1}(z_i), \theta) = \prod f_X(x_i, \theta)$$

Similarly, we have 
$$S_Z(z) = P(Z>z) = P(g(X) > g(x)) = p(X>x) = S(x)$$ 

##### likelihood:

From the above lemma we have the following survival full likelihood function, 
$$L(t) = \prod_{i \in D}f_T(t_i)\prod_{i \in D^c}S_T(t_i) \sim \prod_{i \in D}f_{lnT}(ln(t_i))\prod_{i \in D^c}S_{lnT}(ln(t_i))$$

### PH (proportional hazard)

#### Basic idea:

$$h_1(t) = \lambda h_0(t)$$

### Cox Semi-parametric proportional hazard model
#### Basic idea
$$h_x(t) = e^{x_i\beta}h_0(t) = r(x_i)h_0(t)$$
Here the $$r_i$$, is known as the relative risk function, which is the hazard ratio between $$x_i$$ and the baseline. 

#### partial likelihood
Cox PH model is a semi-parametric model, in the sense that the $$h_0(t)$$ part (the baseline hazard function) in the hazard function is estimated in a non-parametric way. The parametric part of the likelihood function is estimated by solve the MLE of the following partial likelihood function:
$$\prod _j\frac{r(x_j)}{\sum_{i \in R_j}r(x_i)}$$

$$R_j$$ is the cohort of subject at risk at time $$j$$, i.e, they are not censored or died yet.

#### Derivation of the partial likelihood function
https://web.stanford.edu/~lutian/coursepdf/unitcox1.pdf

The full likelihood function of a PH function can be expressed as following:

$$L(t) = \prod _j e^{-H_j(t_j)} h_j(t_j)^{\delta_j}$$

$$\delta_i = 0$$ means a case is censored; if it is 1 then otherwise.

Now assuming that $$t_1 < t_2 <...< t_j$$, we then will have  

$$H_j(t_j) \approx \sum_{i=1}^j h_j(t_i) = \sum_{i=1}^j r(x_j)h_0(t_i)$$ (pay attention to the subscript!)

The above equations lead to 

$$L(t) = \prod _j e^{-H_j(t_j)} h_j(t_j)^{\delta_j} = \prod e^{-\sum_{i=1}^j r(x_j)h_0(t_i)}(r(x_j)h_0(t_j))^{\delta_j} =  \prod e^{-\sum_{i=1}^j r(x_j)h_i}(r(x_j)h_j)^{\delta_j}$$

And

$$l(t) =\sum_j (\delta_j[log(r(x_j)) + log(h_j)] - \sum_{i=1}^jr(x_j)h_i)$$

The above formula of $$l(t)$$ can then be expressed as

$$\sum_j \delta_j[log(r(x_j)) + log(h_j)] -\sum_j\sum_{i=1}^jr(x_j)h_i = \sum_j \delta_j[log(r(x_j)) + log(h_j)] -\sum_jh_j\sum_{i=j}^nr(x_i)$$

By using the **profile likelihood** methodology, we can maximize $$h_i$$ in terms of fixed $$r$$, then replace $$h_i$$ with a function of $$r$$, and we will end up with the partial likelihood function.



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

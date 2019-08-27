
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


## Commonly used distributions for survival parametric models
### exponential distribution
$$f(t) = \lambda e^{-\lambda t}$$

$$S(t) = e^{-\lambda t}$$

$$h(t) = \lambda$$

$$H(t) = \lambda t$$

### weibull distribution
$$f(t) =  \lambda pt^{p-1} e^{-\lambda t^p}$$

$$S(t) = e^{-\lambda t^p}$$

$$h(t)=\lambda p t^{p-1}$$

$$H(t) = \lambda t^p$$

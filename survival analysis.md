
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

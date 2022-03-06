##  Binomial
E = p; V = npq 

sum of B(m, p), B(n,p): B(n+m, p)
## NB
E=rp/q; v=rp/q^2; p(x) = c(x+r-1, r-1)* p^x * q*r

sum of NB(r1, p),. NB(r2,p): NB(r1+r2, p)


## poisson dist
poisson process - number of occurence in a certain period follows a poisson distribution with mean lambda; number of time between two occurence is exponential with mean 1/lambda

sum of negative binomial: 

E = lambda; v=lambda; p(x) = e^(-lambda)lambda^x/x!                                                    

sum of P(lambda1), P(lambda2): P(lambda1 + lambda2)

## exponential dist
f(x) = lambda exp(-lambda * x)

E(x) = 1/lambda; v(x)=1/lambda ^ 2

sum of Exp(lambda1), Exp(lambda2): a special case of gamma distribution


## normal:

f(x) = 1/(sqrt(2pi)sigma) exp(-(x-mu)^2/(2sigma^2))

E(x) = mu; v(x) = sigma^2; mgf = exp(mux+ sigma^2/2 * t^2)

N(mu1, sigma1^2) + N(mu2, simga2^2) = N(mu1+mu2, sigma1^2+sigma^2)


## gamma dist 

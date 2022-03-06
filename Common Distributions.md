## general:

CF to pdf: inverse fourier transformation
https://math.stackexchange.com/questions/925545/determine-the-pdf-from-the-mgf

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


## chi-square

standard normal square is chi-square with df=1

sum of Chi(k1) + Chi(k2) = Chi(k1+k2)


## t distribution

independent N(0,1) / sqrt (Chi(k)) ~ T(n-1)

distribution of sample mean / sample variance is proportional to a t distribution

E(T) = 0; V(T) = mu/mu-2 if mu>2; +inf if mu is between 1 to 2; and otherwise undetermined


## F distribution

F ~ Chi(k1)/k1/(Chi(k2)/k2)

## gamma dist 

f(x) = 1(/gamma(alpha)* beta^alpha)* x^(alpha-1) * exp(-x/beta)

E: alpha * beta; v: alpha * beta ^ 2

mgf: (1-beta * t) ^ alpha; 

sum of G(alpha1, beta) +  G(alpha2, beta) = G (alpha1+alpha2, beta)

gamma function: gamma(alpha) = int (x^(alpha-1) exp(-x))

gamma(alpha+1) = alpha gamma (alpha)

gamma (n+1) = n!


## beta dist


## cauchy dist 

f(x) = 1/(pi * gamma * （1+ (x-x0)^2/gamma^2)）

it has no mean https://en.wikipedia.org/wiki/Cauchy_distribution#Explanation_of_undefined_moments

## tweedie

## relationship between other dists:

### beta and gamma

X~gamma(alpha,1), Y ~ gamma(beta,1), then X/(X+Y) ~ beta (alpha, beta)

on the other hand, lim(n to inf) B(k, n) = ramma(k, 1)

### beta and F
if X ~ beta(alpha1/2, alpha2/2), then alpha2* X /( alpha1 (1-X)) ~ F(alpha1, alpha2)

### tweedie dist

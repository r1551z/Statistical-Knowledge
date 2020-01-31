
# Intro
This md file contains LR related stuff.

ref:

http://users.stat.umn.edu/~helwig/notes/mlr-Notes.pdf


# Assumptions, violation consequences, detections, and remedies.

1. Independence. similary as 2; var(epsilon)!=sigma^2 * I

2. Homoscedasticity: 

  a. consequences: unbiased estimates; if E(\epsilon)=0;
however, OLS estimate will not be BLUE; and inferences will be
wrong.

  b. detection: residual plot vs time / x / prediction


3. Normality: relatively least impact; 
the inference obtained due to normality will be less reliable;
however, the estimate itself will still be quite robust.


# other violations.

1. missing some columns: result will be biased.

2. adding noisy columns: estimation will be unbiased; however, the variance will be enlarged.

# Predictions

1. CI: x*beta +/- t_n-p-1_alpha * \hat{\sigma}} * x'(X'X)^{-1}x


2. PI: x*beta +/- t_n-p-1_alpha * \hat{\sigma}} * (1+x'(X'X)^{-1}x)


# tests

See the repo for linkedinDS


# BLUE

if Homoscedasticity & independence are satisfied, OLS estimate is the BLUE estimate according to 
Gauss-Markov theorem.


# Multicolinearity

output will still be unbiased; however, it will give quite a bit variance, therefore, the beta hat
will vary a lot, and sometimes you will observe reversed signs.




# Intro
This md file contains LR related stuff.

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


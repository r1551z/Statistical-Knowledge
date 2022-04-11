# Basic Principal of design
Randomization, replication and blocking

# Simple comparative analysis

Paired vs randomized design:

Advantage of pair: remove nuisance factors to achive better precision

Disadvantage: lose degree of freedom

When a bad choice: specimen are homogenous


# single ANOVA

## fixed and random

in this case, they turn out to be the same analysis

random: if treatments were randomly picked from a large population and we want to 
extend our conclusion.

## Model adequancy

Residual plot

a. QQ plot - normality assumption

outliers - more detailed investigation; worst case two analysis

b. Residual plot in time sequence - skill of experiment may change

c. Residual vs fitted value - homogeneity; if we need to transform the data

    test of equal variance: Barletts test (sensitive normality) or levene's test (more robust)
    
    if residual proportional to y^(alpha), a usual transformation we can use is y^(1-alpha)
    
    so if residual proportional to sqrt(mu), we choose square root transformation 
    
    if residual proportional to mu, we choose log transformation 
    
 d. residual vs other variables   
    
    if any pattern is shown, then we need to control that variable in the feature or include
    it in analysis
    
## Compare contrasts

test: estimate/variance of estimate

orthorganal contrast: independent test

## compare pairs of treatment means

**Turkey's Test**: control overall significance level; the level will be alpha for balanced design and 
<=alpha if unbalanced design.

significant F but no significant pairwise test result? Since F test consider all contrasts,
probably due to the significant contrast is not mu1-mu2

## estimate model parameter

MSE: sigma

mu: y..

gamma_i: yi. - y..

# balanced vs unbalanced:

balanced desing maximize power and relatively **insensity to departure from normality**

# Randomized Block 

Why: control nuisance factors

randomization: within each block (restricted randomization)

  ## nuisance factor method:
  
    controllable and known: block
    
    uncontrollable but known: ancova
    
    uncontrollable and unknown: randomization
    
  ## Analysis
  
  treatment effect: same as regular anova
  
  block: due to restricted randomization, F test is not very recommended.
  
 Comparison with single variable anova:
 
 as block is not considered, we might end up with a larger MSE  
 
 
## estimate parameters:

like a factorial design without interaction

A: yi.-yii

Block: y.j-y..

## if we have interaction and random effect

  if we think block effect is fixed, interaction could inflate the variance; in which case
  factorial design must be used
  
  if block effect is random, the analysis would not be affected (with or without interaction); also
  it will be the same as fixed effect model without interaction.

## model adequacy

residual vs y: curvy? probably an interaction

## Missing value

impute with the value that can minimize teh 
  
# Latin Square Design

if want to control two nuisance factors at the same time

analysis: same as factorial without interactions

randomization: select a particular latin square (where to place each treatment) at random
    
problem: varaince has a small degree of freedom
    

# Factorial design

randomization: set each sample to a cell by random

advantage: able to evaluation interaction; more efficient compared with one-at-a-time (no replicate needed if we do not have interaction)

## analysis

fixed effects: MSA/MSE; MSB/MSE; MSAB/MSE

one obs per cell: test interaction - SS(error) = SS(residual) - some one degree error due to non-additivity 
(Tukey single-degree-of-freedom test)


random effects: MSA/MSAB; MSB/MSAB; MSAB/MSE

notice here, if one of the variance might be implementing that corresponding effect is null and we want to 
fit a reduced model

mixed model (restricted - the sum of interaction is 0; i.e., not independent):

    fixed: MSA/MSAB

    random: MSB/MSE

mixed model (unrestricted - iteraction and the random effect are iid both; preferred for unbalanced data):

  fixed: MSA/MSAB
  
  random: MSA/MSAB
  
  
## Estimate of parameters

A: yi. bar-yii bar

B: y.j bar-y..bar

AB:yij. bar - yi.. bar-y.j.bar+y..bar
# Nested Model Design

when to use: certain factor levels are available only to certain other factor level; i.e., cannot
do a full randomization cause some cells are not available


## analysis

fixed: MSA/MSE; MSB(A)/MSE


A is fixed and B is random: MSA/MSB(A); MSB(A)/MSE

both random： MSA/MSB(A); MSB(A)/MSE






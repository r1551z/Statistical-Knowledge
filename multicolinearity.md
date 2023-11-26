# issue of multicolinearity

1. for regression, the result will still be unbiased; however, the variance of certain variables will be very big, leading to unrobust result.
2. hard to explain: it is harder to distinguish of effects from highly correlated features.

# remedidation to multicoliearity data

##  nontechnical
1. reduce the input features

2. break it by including more data

3. different encoding method.
4. when explanation, use a method that can group correlated feature together

## methods that can be used to metigate with the problem

1. partial least square regression
a case study: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://iopscience.iop.org/article/10.1088/1742-6596/1463/1/012006/pdf
pls paper: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://personal.utdallas.edu/~herve/Abdi-PLS-pretty.pdf


2. factor analysis 

sorry for reviewing discrete choice model again.

we have $x_i$ $y_j$ and $z_{ij}$

# Micro data

## Cross sectional (single)

$$u_{ij}=\alpha_i+ \alpha x_i +\beta_{j}+ \beta y_{j} + \zeta x_i y_j+\gamma z_{ij} +\epsilon_{ij}$$
We can estimate 
$\alpha, \beta_j,\beta, \zeta,\gamma$.

- application: school choice


## Multiple markets (across location $l$)

If we have micro data, this is the same as the single cross sectional case. Just pool everything tgt.

## Multiple markets (across time $t$)

$$ u_{ijt}=\alpha_i+ \alpha x_{it} +\beta_{j}+  \beta_t+\beta y_{j} + \zeta x_{it} y_j+ \gamma z_{ijt} +\epsilon_{ijt}$$ 

Same idea...we may be able to identify the $\alpha_i$ if $x_{it}$ changes over time.



# Market share data
There's no individual here :) but we can still write individual utility just for the sake of it.
$$ u_{ij} = \alpha_i+ \alpha x_i +\beta_{j}+ \beta y_{j} + \zeta x_i y_j+\gamma z_{ij} +\epsilon_{ij}$$ 

## Cross sectional (single)
The market share takes the same form as the choice probability but no individual characteristics $x_i$.
$$ u_{ij} = \beta_{j}+\beta y_{j} +\epsilon_{ij}$$

Thus 
$$s_{j} = \frac{\exp(\beta_{j}+ \beta y_{j})}{\sum_{j'}\exp(\beta_{j'}+ \beta y_{j'})}$$

$$\log s_{j} -\log s_{0} = \beta_{j}+ \beta y_{j}$$

The moment condition is that 
$$ E[\beta_j y_j]=0$$
Here each $j$ is one observation that can be used to estimate the coeffecients $\beta$. 
Then 
$$\hat{\beta}_j = \log s_{j} -\log s_{0}-\hat{\beta} y_{j}$$

## Multiple markets (across location $l$)

$$ u_{ijl} = \beta_{jl}+\beta y_{j} + \epsilon_{ijl}$$
Thus 
$$s_{jl} = \frac{\exp(\beta_{jl}+  \beta y_{j})}{\sum_{j'l}\exp(\beta_{j'l}+ \beta y_{j'})}$$
$$\log s_{jl} -\log s_{0l} = \beta_{jl}+ \beta y_{j}$$
Here each $jl$ is one observation that can be used to estimate the coeffecient $\beta$.

The moment condition is that 
$$E[\beta_{jl} y_{j}]=0$$

## Multiple markets (across time $t$)

Same as above but with $t$. However, we may want to assume some structure between $\beta_{jt}$ and $\beta_{jt-1}$ which may be of help in estimation.

# Appendix
## Multinomial logistic regression

According to the [wikipedia page](
https://en.wikipedia.org/wiki/Multinomial_logistic_regression#Estimating_the_coefficients),there are **three** ways to look at this regression model: 
1. As a set of independent binary regressions (the odds-ratio)
$${\displaystyle \ln {\frac {\Pr(Y_{i}=k)}{\Pr(Y_{i}=K)}}\,=\,{\boldsymbol {\beta }}_{k}\cdot \mathbf {X} _{i},\;\;\;\;\;\;1\leq k<K}$$
1. As a log linear model 
$${\displaystyle \ln \Pr(Y_{i}=k)={\boldsymbol {\beta }}_{k}\cdot \mathbf {X} _{i}-\ln Z,\;\;\;\;\;\;1\leq k\leq K.}$$
1. As a latent variable model
$${\displaystyle Y_{i,k}^{\ast }={\boldsymbol {\beta }}_{k}\cdot \mathbf {X} _{i}+\varepsilon _{k}\;\;\;\;,\;\;k\leq K}$$

Check [this chapter](https://eml.berkeley.edu/choice2/ch3.pdf) of the train textbook for the derivation of the choice probability. Then estimation is done by maximum likelihood.

# Regression_Technical_details

Regression models involve the following variables:

The unknown parameters, denoted as {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }}, which may represent a scalar or a vector.
The independent variables, {\displaystyle \mathbf {X} } \mathbf {X} .
The dependent variable, {\displaystyle Y} Y.
In various fields of application, different terminologies are used in place of dependent and independent variables.

A regression model relates {\displaystyle Y} Y to a function of {\displaystyle \mathbf {X} } \mathbf {X}  and {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }}.

{\displaystyle Y\approx f(\mathbf {X} ,{\boldsymbol {\beta }})} {\displaystyle Y\approx f(\mathbf {X} ,{\boldsymbol {\beta }})}
The approximation is usually formalized as {\displaystyle E(Y|\mathbf {X} )=f(\mathbf {X} ,{\boldsymbol {\beta }})} {\displaystyle E(Y|\mathbf {X} )=f(\mathbf {X} ,{\boldsymbol {\beta }})}. To carry out regression analysis, the form of the function {\displaystyle f} f must be specified. Sometimes the form of this function is based on knowledge about the relationship between {\displaystyle Y} Y and {\displaystyle \mathbf {X} } \mathbf {X}  that does not rely on the data. If no such knowledge is available, a flexible or convenient form for {\displaystyle f} f is chosen.

Assume now that the vector of unknown parameters {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }} is of length {\displaystyle k} k. In order to perform a regression analysis the user must provide information about the dependent variable {\displaystyle Y} Y:

If {\displaystyle N} N data points of the form {\displaystyle (Y,\mathbf {X} )} {\displaystyle (Y,\mathbf {X} )} are observed, where {\displaystyle N<k} {\displaystyle N<k}, most classical approaches to regression analysis cannot be performed: since the system of equations defining the regression model is underdetermined, there are not enough data to recover {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }}.
If exactly {\displaystyle N=k} {\displaystyle N=k} data points are observed, and the function {\displaystyle f} f is linear, the equations {\displaystyle Y=f(\mathbf {X} ,{\boldsymbol {\beta }})} {\displaystyle Y=f(\mathbf {X} ,{\boldsymbol {\beta }})} can be solved exactly rather than approximately. This reduces to solving a set of {\displaystyle N} N equations with {\displaystyle N} N unknowns (the elements of {\displaystyle {\boldsymbol {\beta }})} {\displaystyle {\boldsymbol {\beta }})}, which has a unique solution as long as the {\displaystyle \mathbf {X} } \mathbf {X}  are linearly independent. If {\displaystyle f} f is nonlinear, a solution may not exist, or many solutions may exist.
The most common situation is where {\displaystyle N>k} {\displaystyle N>k} data points are observed. In this case, there is enough information in the data to estimate a unique value for {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }} that best fits the data in some sense, and the regression model when applied to the data can be viewed as an overdetermined system in {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }}.
In the last case, the regression analysis provides the tools for:

Finding a solution for unknown parameters {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }} that will, for example, minimize the distance between the measured and predicted values of the dependent variable {\displaystyle Y} Y (also known as method of least squares).
Under certain statistical assumptions, the regression analysis uses the surplus of information to provide statistical information about the unknown parameters {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }} and predicted values of the dependent variable {\displaystyle Y} Y.
Necessary number of independent measurements[edit]
Consider a regression model which has three unknown parameters, {\displaystyle \beta _{0}} \beta _{0}, {\displaystyle \beta _{1}} \beta _{1}, and {\displaystyle \beta _{2}} \beta _{2}. Suppose an experimenter performs 10 measurements all at exactly the same value of independent variable vector {\displaystyle \mathbf {X} } \mathbf {X}  (which contains the independent variables {\displaystyle X_{1}} X_{1}, {\displaystyle X_{2}} X_{2}, and {\displaystyle X_{3}} X_3). In this case, regression analysis fails to give a unique set of estimated values for the three unknown parameters; the experimenter did not provide enough information. The best one can do is to estimate the average value and the standard deviation of the dependent variable {\displaystyle Y} Y. Similarly, measuring at two different values of {\displaystyle \mathbf {X} } \mathbf {X}  would give enough data for a regression with two unknowns, but not for three or more unknowns.

If the experimenter had performed measurements at three different values of the independent variable vector {\displaystyle \mathbf {X} } \mathbf {X} , then regression analysis would provide a unique set of estimates for the three unknown parameters in {\displaystyle {\boldsymbol {\beta }}} {\boldsymbol {\beta }}.

In the case of general linear regression, the above statement is equivalent to the requirement that the matrix {\displaystyle \mathbf {X} ^{\top }\mathbf {X} } {\displaystyle \mathbf {X} ^{\top }\mathbf {X} } is invertible.


Linear regression[edit]
Main article: Linear regression
See simple linear regression for a derivation of these formulas and a numerical example
In linear regression, the model specification is that the dependent variable, {\displaystyle y_{i}} y_{i} is a linear combination of the parameters (but need not be linear in the independent variables). For example, in simple linear regression for modeling {\displaystyle n} n data points there is one independent variable: {\displaystyle x_{i}} x_{i}, and two parameters, {\displaystyle \beta _{0}} \beta _{0} and {\displaystyle \beta _{1}} \beta _{1}:

straight line: {\displaystyle y_{i}=\beta _{0}+\beta _{1}x_{i}+\varepsilon _{i},\quad i=1,\dots ,n.\!} y_{i}=\beta _{0}+\beta _{1}x_{i}+\varepsilon _{i},\quad i=1,\dots ,n.\!
In multiple linear regression, there are several independent variables or functions of independent variables.

Adding a term in {\displaystyle x_{i}^{2}} {\displaystyle x_{i}^{2}} to the preceding regression gives:

parabola: {\displaystyle y_{i}=\beta _{0}+\beta _{1}x_{i}+\beta _{2}x_{i}^{2}+\varepsilon _{i},\ i=1,\dots ,n.\!} y_{i}=\beta _{0}+\beta _{1}x_{i}+\beta _{2}x_{i}^{2}+\varepsilon _{i},\ i=1,\dots ,n.\!
This is still linear regression; although the expression on the right hand side is quadratic in the independent variable {\displaystyle x_{i}} x_{i}, it is linear in the parameters {\displaystyle \beta _{0}} \beta _{0}, {\displaystyle \beta _{1}} \beta _{1} and {\displaystyle \beta _{2}.} \beta _{2}.

In both cases, {\displaystyle \varepsilon _{i}} \varepsilon _{i} is an error term and the subscript {\displaystyle i} i indexes a particular observation.

Returning our attention to the straight line case: Given a random sample from the population, we estimate the population parameters and obtain the sample linear regression model:

{\displaystyle {\widehat {y}}_{i}={\widehat {\beta }}_{0}+{\widehat {\beta }}_{1}x_{i}.} {\displaystyle {\widehat {y}}_{i}={\widehat {\beta }}_{0}+{\widehat {\beta }}_{1}x_{i}.}
The residual, {\displaystyle e_{i}=y_{i}-{\widehat {y}}_{i}} e_{i}=y_{i}-{\widehat {y}}_{i}, is the difference between the value of the dependent variable predicted by the model, {\displaystyle {\widehat {y}}_{i}} {\displaystyle {\widehat {y}}_{i}}, and the true value of the dependent variable, {\displaystyle y_{i}} y_{i}. One method of estimation is ordinary least squares. This method obtains parameter estimates that minimize the sum of squared residuals, SSE,[22][23] also sometimes denoted RSS:

{\displaystyle SSE=\sum _{i=1}^{n}e_{i}^{2}.\,} SSE=\sum _{i=1}^{n}e_{i}^{2}.\,
Minimization of this function results in a set of normal equations, a set of simultaneous linear equations in the parameters, which are solved to yield the parameter estimators, {\displaystyle {\widehat {\beta }}_{0},{\widehat {\beta }}_{1}} {\widehat {\beta }}_{0},{\widehat {\beta }}_{1}.


Illustration of linear regression on a data set.
In the case of simple regression, the formulas for the least squares estimates are

{\displaystyle {\widehat {\beta }}_{1}={\frac {\sum (x_{i}-{\bar {x}})(y_{i}-{\bar {y}})}{\sum (x_{i}-{\bar {x}})^{2}}}{\text{ and }}{\widehat {\beta }}_{0}={\bar {y}}-{\widehat {\beta }}_{1}{\bar {x}}} {\displaystyle {\widehat {\beta }}_{1}={\frac {\sum (x_{i}-{\bar {x}})(y_{i}-{\bar {y}})}{\sum (x_{i}-{\bar {x}})^{2}}}{\text{ and }}{\widehat {\beta }}_{0}={\bar {y}}-{\widehat {\beta }}_{1}{\bar {x}}}
where {\displaystyle {\bar {x}}} {\bar {x}} is the mean (average) of the {\displaystyle x} x values and {\displaystyle {\bar {y}}} {\bar {y}} is the mean of the {\displaystyle y} y values.

Under the assumption that the population error term has a constant variance, the estimate of that variance is given by:

{\displaystyle {\hat {\sigma }}_{\varepsilon }^{2}={\frac {SSE}{n-2}}.\,} {\hat {\sigma }}_{\varepsilon }^{2}={\frac {SSE}{n-2}}.\,
This is called the mean square error (MSE) of the regression. The denominator is the sample size reduced by the number of model parameters estimated from the same data, {\displaystyle (n-p)} {\displaystyle (n-p)} for {\displaystyle p} p regressors or {\displaystyle (n-p-1)} {\displaystyle (n-p-1)} if an intercept is used.[24] In this case, {\displaystyle p=1} p=1 so the denominator is {\displaystyle n-2} n-2.

The standard errors of the parameter estimates are given by

{\displaystyle {\hat {\sigma }}_{\beta _{0}}={\hat {\sigma }}_{\varepsilon }{\sqrt {{\frac {1}{n}}+{\frac {{\bar {x}}^{2}}{\sum (x_{i}-{\bar {x}})^{2}}}}}} {\hat {\sigma }}_{\beta _{0}}={\hat {\sigma }}_{\varepsilon }{\sqrt {{\frac {1}{n}}+{\frac {{\bar {x}}^{2}}{\sum (x_{i}-{\bar {x}})^{2}}}}}
{\displaystyle {\hat {\sigma }}_{\beta _{1}}={\hat {\sigma }}_{\varepsilon }{\sqrt {\frac {1}{\sum (x_{i}-{\bar {x}})^{2}}}}.} {\hat {\sigma }}_{\beta _{1}}={\hat {\sigma }}_{\varepsilon }{\sqrt {\frac {1}{\sum (x_{i}-{\bar {x}})^{2}}}}.

Other methods[edit]
Although the parameters of a regression model are usually estimated using the method of least squares, other methods which have been used include:

Bayesian methods, e.g. Bayesian linear regression
Percentage regression, for situations where reducing percentage errors is deemed more appropriate.[28]
Least absolute deviations, which is more robust in the presence of outliers, leading to quantile regression
Nonparametric regression, requires a large number of observations and is computationally intensive
Distance metric learning, which is learned by the search of a meaningful distance metric in a given input space.[29]

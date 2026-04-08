# REGRESSION

Is the variable X (or more likely, X1, ..., Xp) associated with a variable Y, and if so, what is the relationship and can we use it to predict Y?



while correlation measures the strength of an association between two variables, regression

quantifies the nature of the relationship.



Simple linear regression tries to find the “best” line to predict the response PEFR as a

function of the predictor variable Exposure



Intercept is the predicted Y is when X = 0

slope or coefficient: for each extra unit of X how much Y changes (increase or decrease)



fitted values (the predictions) and residuals (prediction errors)

residuals = Actual - predicted

scikit-learn expects the input X to be a 2-dimensional array: (number\_of\_samples, number\_of\_features) OR (elements, axis) OR (rows, columns)



The regression line is the estimate that minimizes the **sum of squared residual values**,

also called the **residual sum of squares or RSS**

The method of minimizing the sum of the squared residuals is termed **least squares**

**regression**, or **ordinary least squares (OLS) regression**



Least squares, like the mean are sensitive to outliers; although significant problem only in small or moderate-sized data sets.

In **Explanatory model** the main focus is the **estimated slope**

In **Predictive models,** the main focus is the **Predicted values**



The regression equation does not prove the direction of causation; Maybe there are other factors

Causation must be inferred from context, experiments, and domain knowledge...think about confounders too





The most important performance metric from a data science perspective is **root mean**

**squared error**, or **RMSE;** measures overall accuracy; typical prediction error

Similar to RMSE is the **residual standard error**, or **RSE**. Small difference between both, especially for big data

RMSE/range; something like 20% is a fairly large prediction error



r2 measures how well the model explains the variability in the target variable. Also known as **Coefficient of Determination**

r2 = 1 - (unexplained variance / total variance)

How much better is the model compared to just predicting the mean?

Overfitting can still give high R²



Both libraries (sklearn and statsmodels) typically use ordinary least squares and produce very similar coefficients.



*...the model only improves predictions by \~7.7% compared to predicting the mean.*



Noise → randomness / unobserved factors / measurement error. Unexplained variability

is my RMSE percentage acceptable by some standard" VS What is the cost of being wrong by this amount in my specific use case?





**Penalized Regression** adds a constraint that penalizes the model for too many variables

It doesn't remove predictor variables, it just reduces them, sometimes to 0

*Rigde* and *Lasso* are good examples of penalized regression





Subset and stepwise regression have the potential of overfitting; reminds us of a form of **selection bias** known

as **vast search effect**

A solution to this is cross-validation or target shuffling



Cross-validation becomes your selection criterion, replacing AIC or R²





Check list

* Model selection: stepwise or subset VS Penalized
* Overfitting issue
* Extrapolation
* Weighted Regression?
* Confidence Interval vs Prediction Interval
* Correlated Predictors and Multicolinearlity





**Confidence Interval**: intervals around regression parameters (coefficients)

**Prediction Interval:** intervals around predicted y values





One-hot encoding creates a column for every category, while reference coding drops one category and expresses everything relative to it

One-hot encoding is perfect for Neural networks, tree-based models (decision tree, random forest), distance-based models (k-nearest neighbours), clustering etc



* Factor variables
* Factor variables with many levels
* Ordered factor variables





**Ridge (L2) Regression**

What problem does it solve

Your model is overfit to the training data but has a high variance (sum of squared residuals) with the test data

You introduce some bias (penalty term) to how the line is fit to the data

Basically, **we find a line that doesn't fit the training data too well.** Start with a slightly worse fit and gain better predictions in the long run



sum of squared residuals + (lambda + slope squared)

The smaller the slope of a predictor, the less sensitive the outcome is to it.

Ridge regression lines usually have a smaller slope than OLS line

Increasing lambda generally further reduces the slope.

We choose the best lambda using cross validation



Use Ridge regression when your training set is small



**Lasso (L1) Regression**

Just like ridge regression but uses |slope| instead of slope squared

Has the ability to take the slope to 0 and remove the predictor totally, unlike ridge

we can at best take it close to 0



Lasso regression when we have a lot of useless variables



**Regularization signals**

1. Overfitting
2. Too many predictors relative to observations (high dimensionality)
3. Multicolinearlity
4. Large or “weird” coefficients
5. Stepwise / subset selection feels unstable
6. You care about prediction, not inference
7. Validation performance improves with shrinkage





Always examine the regression equation; understand the relationships between predictors and outcome

Try and make sense of things. Like, why would the coefficient of bedrooms be negative



*In multiple regression, the predictor variables are often correlated with each other*



**multicollinearity**: a condition in which there is redundance among the predictor variables. Caused by

* mistakenly adding a variable twice
* using P dummy variables instead of P - 1
* Two variables have almost perfect correlation







How much the variance of a coefficient is inflated due to multicollinearity

High VIF - this feature is redundant given others; Can this variable be explained by ALL the others?



What **Unstable** means as per coefficients

* surprisingly large magnitudes
* Wrong signs
* Coefficients that contradict domain knowledge



But there’s still \~40% unexplained (likely nonlinearities, missing features, noise)











https://claude.ai/share/7a2ceddc-92c0-4e22-9bca-a2ac88b070b5


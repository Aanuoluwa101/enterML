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



*...the model only improves predictions by ~7.7% compared to predicting the mean.*



Noise → randomness / unobserved factors / measurement error. Unexplained variability

is my RMSE percentage acceptable by some standard" VS What is the cost of being wrong by this amount in my specific use case?


# Regression side-notes

*The things here are intended to be punchy*



We started with simple linear regression - RMSE and r2 are ok

But now we've started adding more variables - we need to use AIC or r2 adjusted 

But then, cross-validation is still better 





In multiple linear regression, when you add more variables (features), you are giving the model more flexibility to fit the data.

*More flexibility = the model can adjust itself better to match the training data*



cross val score: what is this model's average performance on unseen data



Lasso and Ridge don't search through models. They solve one model

STEPWISE vs PENALIZED: https://claude.ai/share/7a2ceddc-92c0-4e22-9bca-a2ac88b070b5  or https://claude.ai/chat/54335d24-7269-477d-b3d1-99c80726b926





AIC is only meaningful for comparison: the AIC of one model vs the AIC of another



**The inability of a machine learning method to capture the** 

**true relationship is called bias**



Bias = the model’s built-in assumptions causing it to systematically miss the truth

I’m going to interpret the world as linear… no matter what





**Variance = how much a model’s predictions change when trained on different datasets**

Low variance means the sum of squares are similar for different datatsets



Usually we're aiming for low bias and low variability

We try to find the sweet spot between a simple (high bias) and a complex (high variance) models

using methods like regularization, bagging and boosting


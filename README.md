# Analysis of the `quine` Dataset Using Gamma Regression, Negative Binomial and Log Normal Models

This project segment focuses on the analysis of the `quine` dataset from the `MASS` package in R, specifically examining the number of days students were absent from school (`Days`). A Gamma regression model with a log link was employed to understand the impact of various predictors on absenteeism.

## Objective

The main goal is to determine the best statistical model to explain the variability in the `Days` variable, comparing Gamma regression with other models like Negative Binomial and Log-Normal.

## Dataset Introduction

The [quine dataset]() contains data on the absenteeism among elementary school children. It includes several key variables:
- **Days:** The number of days a student was absent during the school year.
- **Eth:** The ethnic background of the student, categorized into groups.
- **Sex:** The gender of the student, recorded as male or female.
- **Age:** The age group of the student, indicating their grade level.
- **Lrn:** The learning status of the student, indicating if they are a slow or fast learner.

## Methodology

1. **Model Fitting:** A Gamma regression model was fitted to `Days` with `Eth`, `Sex`, `Age`, and `Lrn` as predictors.
2. **Handling Zero Counts:** To address zero counts in `Days`, small constants (0.01, 0.05, 0.1) were experimented with, and 0.1 was selected based on its performance in reducing residual deviance and AIC.
3. **Stepwise Model Selection:** The stepwise AIC method, adjusted with `k=log(146)`, was used to refine the model and prevent overfitting in large datasets.

## Results

- **Model Choice:** The Gamma regression model was chosen as the best fit after testing different constants to handle zero counts and using stepwise AIC for model selection.
- **Model Comparison:**
  - **Negative Binomial vs. Gamma Regression:** Despite the Negative Binomial model having a lower deviance, its complexity and higher number of terms led to the selection of the simpler Gamma model.
  - **Log-Normal vs. Gamma Regression:** The Gamma model was preferred due to lower deviance and fewer terms, making it easier to interpret and fit the data effectively.

## Discussion

The Gamma regression model provided a suitable fit for the `quine` dataset, demonstrating that adjustments for zero counts and careful model selection are crucial in predictive modeling. The comparisons with Negative Binomial and Log-Normal models highlighted the importance of balancing model simplicity with the ability to capture the underlying data patterns.

## Conclusion

The analysis affirmed the effectiveness of Gamma regression in handling data with varying absence days, with `Eth`, `Sex`, `Age`, and `Lrn` as significant predictors. This approach ensures a robust model that is interpretable and adequately represents the data compared to more complex alternatives.

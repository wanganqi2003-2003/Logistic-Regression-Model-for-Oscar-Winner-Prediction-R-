# Oscar Best Picture Winner Prediction

Coursework project for a statistics module — using logistic regression to predict which film wins Best Picture at the Oscars, based on historical nomination and award data from 1928–2024.

## What I did

- Cleaned and prepped the dataset (614 films, 68 variables), removing non-predictive columns
- Fit a full logistic regression model, then used forward stepwise selection (AIC) to narrow it down to 10 meaningful predictors
- Evaluated the model with ROC/AUC analysis — got an AUC of 0.916, sensitivity of 87.5%, specificity of 80.1%
- Used the model to predict 2024 Best Picture odds, normalized so probabilities sum to 1 across nominees in a given year
- Logistic regression assumes independent binary outcomes, but only one film can win per year — so I also built a Random Forest model as an alternative and compared results

## Result

Both models picked *Anora* as the most likely winner, with the logistic regression model giving it a 57.5% chance and Random Forest giving it 23.7% (Random Forest spread probability more evenly across top contenders).

## Files

- `oscar_analysis.R` — full code
- `oscars.csv` — dataset
- Figures — model output, ROC curve, prediction tables

## Method notes

Variable selection used AIC-based forward stepwise regression rather than picking predictors by hand, to balance fit against overfitting. Model comparison (logistic vs. Random Forest) was based on how well each handles the fact that Oscar outcomes are mutually exclusive within a year, not independent binary events.

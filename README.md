# econ3916-lab19-random-forests

# Tree-Based Models: Random Forests

## Objective
I compared tree-based and linear models for predicting California house values, and looked at which features each model relies on.

## Methodology
- Fit a single decision tree, OLS, Ridge and a random forest on California Housing and compared train and test RMSE and R².
- Compared impurity (MDI) importance with permutation importance on the forest.
- Tuned the forest's max_depth and max_features by cross-validation.
- Wrote my own prompt asking an AI for a feature-importance chart function, went 1 round, and checked its output against my permutation importance numbers.

## Key Findings
The single tree memorized the training data. Its test R² was 0.6228, against 0.5758 for Ridge and 0.8046 for the forest. The forest beating Ridge with the same eight features tells me house values depend on the features in nonlinear ways that a linear model misses.

MDI and permutation importance disagreed on some features. Latitude scored 0.0890 by MDI but 0.4427 by permutation, because MDI is computed on training data and permutation importance is measured on the test set.

Tuning the forest by cross-validation raised test R² to 0.8094. In the grid, max_depth mattered more than max_features.

The AI's chart function matched my numbers. Every check said yes: Step 3's values and order at k = 8 and k = 3, no forests fitted, and the same results as permutation_importance on a different tree and rows.

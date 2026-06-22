# Choosing a Loss Function for Gradient Boosting Regression

A short case study on robustness: comparing squared-error, Huber, and quantile loss
in scikit-learn's `GradientBoostingRegressor` on a dataset of commercial building energy use.

## Summary

Default loss functions in gradient boosting (squared error) are sensitive to
outliers and contaminated training labels. This project tests whether switching
to Huber or quantile loss actually improves recovery of the true underlying
relationship when around 5% of training rows are corrupted (equipment faults, building
closures). Result: Huber loss cuts the error against the true signal roughly in
half compared to squared error, consistently across multiple train/test splits
and a wide range of hyperparameters.

## Repository contents

File , Description

`tutorial.ipynb` Full analysis: data generation, EDA, baseline, three loss-function variants, robustness checks, interpretability.
`tutorial.pdf` Written summary of the method and findings.
`building_energy_dataset.csv` The dataset used.
`LICENSE` MIT License.

## Dataset

daily energy-use data for a commercial building (1,100 rows),
Features: outdoor temperature, occupancy rate,
humidity, solar irradiance, weekend flag. Target: daily energy use (kWh).

## Getting started

Requirements: Python 3.9+, numpy, pandas, matplotlib, scikit-learn, jupyter

pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook tutorial.ipynb

## Key references

- Friedman, J. H. (2001). Greedy function approximation: A gradient boosting machine. *Annals of Statistics*, 29(5), 1189–1232.
- Huber, P. J. (1964). Robust estimation of a location parameter. *Annals of Mathematical Statistics*, 35(1), 73–101.
- Koenker, R., & Bassett, G. (1978). Regression quantiles. *Econometrica*, 46(1), 33–50.

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
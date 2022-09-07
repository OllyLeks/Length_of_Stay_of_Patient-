# Predicting hospital length-of-stay at time of admission

  

## Project Overview

Predictive analytics is an increasingly important tool in the healthcare field since modern machine learning (ML) methods can use large amounts of available data to predict individual outcomes for patients. For example, ML predictions can help healthcare providers determine likelihoods of disease, aid in diagnosis, recommend treatment, and predict future wellness. For this project, I chose to focus on a more logistical metric of healthcare, hospital length-of-stay (LOS). LOS is defined as the time between hospital admission and discharge measured in days.

**The goal of this project is to create a model that predicts the length-of-stay for each patient at time of admission.** The project makes use of the [MIMIC](https://mimic.physionet.org/) database: "MIMIC is an openly available dataset developed by the MIT Lab for Computational Physiology, comprising de-identified health data associated with ~40,000 critical care patients. It includes demographics, vital signs, laboratory tests, medications, and more."

## Summary of Results

I fit five different regression models (from the scikit-learn library) using default settings and compared the r-squared (R2) scores. The GradientBoostingRegressor took the win with an R2 score of ~37% with the testing set so I decided to focus on refining this particular ensemble model. The root mean squared error (RMSE) was used to compare the prediction model versus the industry standard average and median LOS metrics. The gradient boosting model RMSE is better by more than 24% (percent difference) versus the constant average or median models.

<img src="images/RMSE_compare.png" />

Another way I looked at the model was to plot the proportion of accurate predictions in the test set versus an allowed margin of error. Other studies qualify a LOS prediction as correct if it falls within a certain margin of error. It follows that as the margin of error allowance increases, so should the proportion of accurate predictions for all models. The gradient boosting prediction model performs better than the other constant models across the margin of error range up to 50%.

<img src="images/rms_comparison.png" />


## Getting Started

Cloning the git repository and installing the provided packages will help you get a copy of the project up and running on your local machine. The analysis for this project was performed using Jupyter Notebook (.ipynb) and the packages were managed using the Ananconda platform. 

```
git clone https://github.com/daniel-codes/hospital-los-predictor
pip install -r /path/to/requirements.txt
```



## Authors

- **Tunde Oladipupo** -

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

MIMIC-III, a freely accessible critical care database. Johnson AEW, Pollard TJ, Shen L, Lehman L, Feng M, Ghassemi M, Moody B, Szolovits P, Celi LA, and Mark RG. Scientific Data (2016). DOI: 10.1038/sdata.2016.35. Available from: http://www.nature.com/articles/sdata201635


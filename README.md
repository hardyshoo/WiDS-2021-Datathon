# WiDS-2021-Datathon

This is a summary of the code and processes I used to generate submissions for the [WiDS 2021 Datathon](https://www.kaggle.com/c/widsdatathon2021/). My final score was .87461 AUC, good enough for 9th place out of 762 teams.

## Modeling Process

The original dataset was enhanced with manual feature engineering based on the structure of the data, along with MICE imputation of a few key variables. From there, some irrelevant features were filtered out through an iterative process of building a catboost model and using permutation importance to identify variables with negative contribution to the AUC. This filtered data was then used to build Catboost and LightGBM models, using Optuna to help with hyperparameter tuning. Final submission was an average of 2 LightGBM models and 1 CatBoost model. If you're interested in a more detailed walkthrough, check out [my Kaggle post](https://www.kaggle.com/c/widsdatathon2021/discussion/223276).

## Notebooks

* The Data Cleaning and Feature Engineering notebook covers all of the data cleaning and feature engineering operations.
* The Permutation Importance and Correlation analysis notebooks were used for the aforementioned iterative variable selection process.
* The Catboost and LightGBM Model notebooks were used to create Catboost and LightGBM models, respectively.
* The LGBM Hyperparameter Tuning notebook shows how Optuna was used to search for optimal hyperparameters for LightGBM models. Similar code was used to tune parameters for the Catboost model.

## Acknowledgments

* Thanks to [Women in Data Science](https://www.widsconference.org/) and Kaggle for hosting the competition.
* Thanks to the Kaggle community for the thoughtful discussions and great ideas shared throughout. Special thanks to [this kernel](https://www.kaggle.com/siavrez/2020fatures) for some of the feature engineering ideas.

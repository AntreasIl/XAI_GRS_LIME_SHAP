Explainability in Group Recommender Systems using LIME and SHAP

Bachelor Thesis investigating how LIME and Exact SHAP explanations of individual movie-rating predictions affect group recommendations.

## Project Overview 

This project uses MovieLens 100k dataset. An initial SVD based recommender model which generates group movie rankings using Average and Least Misery aggregation. The main explanation experiments used item-based KNN predictor. Which allows selected features to be temporarely removed without retraining the model.

The experiments evaluate 240 groups of 4 users (80 simillar, dissimilar and random). Which gives 960 individual user-movie cases. Five historical ratings are used as explanation features. The evaluation covers individual and group-score fidelity. LIME stability across five random seeds and the computational cost of LIME and Exact SHAP. The KNN explanation experiments evaluate changes in scores for selected movies and not changes in the recommendation rankings.

## Notebooks

1]data_research.ipynb  explores MovieLens dataset
2]recommender_model.ipynb  initial SVD, creates the original gorups and generates group recommendations
3]group_fix fixes.ipynb the insufficient similarity of random groups
4]experiments.ipynb implements KNN, LIME and Exact SHAP explanations and exxperiments for fidelity, stability and cost

Expected folder structure:

project/
├── notebooks/
│   ├── data_research.ipynb
│   ├── recommender_model.ipynb
│   ├── group_fix.ipynb
│   └── experiments.ipynb
├── data/
│   └── ml-100k/
│       ├── u.data
│       ├── u1.base
│       ├── u1.test
│       └── ...
├── results/
│   └── ...
└── README.md

Download and extract MovieLens 100k from GroupLens into data/ml-100k/ 

## Python enviroment:

The notebooks require Python and Jupyter plus packages pandas, numpy, matplotlib, scikit-suprise, lime and shap

From the project directory, create and activate a virtual enviroment (windows powershell):

python -m venv .venv

.\.venv\Scripts\Activate.ps1

python -m pip install pandas numpy matplotlib scikit-surprise lime shap notebook

## Results
The results directory contains the outputs referenced by the notebooks including:
-groups_revised.csv final groups
-full_cases.csv user-movie cases
-full_individual_fidelity.csv individual explanation fidelity
-full_group_fidelity.csv fidelity after average and least misery
-full_stability_cost.csv LIME stability and LIME/SHAP costs
-group_fidelity.png result figures
-least_misery_active.png result figures


The full experiments are computationally expensive. To inspect reported findings use the saved csv files. Avoid using Run All unless you intend to redo the experiments. Some notebook cells depend on previous cells.

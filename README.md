# nfl-big-data-bowl-2019

The goal of this repository is to evaluate the 2017-2019 rushing data from the 
[2019 NFL 
Big Data Bowl](https://www.kaggle.com/c/nfl-big-data-bowl-2020/overview) 
Kaggle competition and answer the following questions:

1. Which teams and players had the most rushing yards?
2. Which offensive personal and defensive personal led to the most rushing 
yards?
3. How well can we predict the yardage from a running play?
4. Which data features influence the yardage predictions the most?

# Setup

This setup assumes Python 3 is installed and that you are using MacOS.

Activate virtual environment:  
`source ./nfl-venv/bin/activate`

The `requirements.txt` lists the dependencies for this project.

# Data

Due to the size of the data, the CSV file won't be stored in the repository. 
Instead, download the training data from 
[here](https://www.kaggle.com/c/nfl-big-data-bowl-2020/data), unzip it, 
and store it in the `data` directory.

Information on the data columns can be found in the link above.

# Notebooks

The `notebooks` directory contains Jupyter notebooks which are used to 
evaluate, preprocess, and model the data.

* `exploratory_data_analysis.ipynb`: Evaluates the data, preprocesses it, 
and answers questions (1) and (2) above. The notebook also outputs the 
preprocessed data to the `data` directory but this file is not saved in the 
repository due to the size.

* `models.ipynb`: Using the preprocessed data file, this notebooks builds two 
models, decision tree and random forest, to predict the yardage from a run 
while extracting the most important features from each model. 
This notebook answers questions (3) and (4) above. The final model is saved 
to the `objects` directory as a pickle file.

# Results

1. Which teams and players had the most rushing yards?
2. Which offensive personal and defensive personal led to the most rushing 
yards?
3. How well can we predict the yardage from a running play?
4. Which data features influence the yardage predictions the most?


# TODOs
[X] Complete `exploratory_data_analysis.ipynb`  
[X] Complete `models.ipynb`  
[ ] Summarize findings  
[ ] Reload `requirements.txt`    
[ ] Reload `nfl-env`  
[ ] Run linter check: `pycodestyle`  
[ ] Run linter check: `pydocstyle`
# nfl-big-data-bowl-2019

The goal of this repository is to evaluate the rushing data from the [2019
NFL Big Data Bowl](https://www.kaggle.com/c/nfl-big-data-bowl-2020/overview) 
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

# TODOs
[ ] Reload `requirements.txt`  
[ ] Run linter check: `pycodestyle`  
[ ] Run linter check: `pydocstyle`
# Business Understanding
The goal of this repository is to evaluate the 2017-2019 rushing data from the 
[2019 NFL 
Big Data Bowl](https://www.kaggle.com/c/nfl-big-data-bowl-2020/overview) 
Kaggle competition and answer the following questions:

1. Which teams and players had the most rushing yards?
2. Which offensive personal and defensive personal led to the most rushing 
yards?
3. How well can we predict the yardage from a running play?
4. Which data features influence the yardage predictions the most?

# Data Understanding

Due to the size of the data, the CSV file won't be stored in the repository. 
Instead, download the training data from 
[here](https://www.kaggle.com/c/nfl-big-data-bowl-2020/data), unzip it, 
and store it in the `data` directory.

Information on the data columns can be found in the link above.

# Setup

This setup assumes Python 3 is installed and that you are using MacOS.

Activate virtual environment:  
`source ./nfl-venv/bin/activate`

The `requirements.txt` lists the dependencies for this project.

The `notebooks` directory contains Jupyter notebooks which are used to 
evaluate, preprocess, and model the data.

# Prepare Data
`exploratory_data_analysis.ipynb`: Evaluates the data, preprocesses it, 
and answers questions (1) and (2) above. The notebook also outputs the 
preprocessed data to the `data` directory but this file is not saved in the 
repository due to the size.

# Data Modeling
`models.ipynb`: Using the preprocessed data file, this notebooks builds two 
models, decision tree and random forest, to predict the yardage from a run 
while extracting the most important features from each model. 
This notebook answers questions (3) and (4) above. The final model is saved 
to the `objects` directory as a pickle file.

# Evaluate the Results

### Which teams and players had the most rushing yards?
The top rushing teams over this span include the following:
* Los Angeles (LA): 4,875
* New Orleans (NO): 4,870
* San Francisco (SF): 4,862
* Baltimore (BLT): 4,843
* New England (NE): 4,820

The top rushing players over this span include the following:
* Ezekiel Elliott: 3,283 
* Todd Gurley: 3,054 
* Christian McCaffrey: 2,613

### Which offensive and defensive personnel led to the most rushing yards?
The **offensive personnel**, with the most total yards, is the "1 RB, 1 TE, 3 WR" 
formation. However, this occurs because it is the most common and shows up 
almost twice as much as the next most frequent personnel. Looking at the 
average yards per format, "1 RB, 0 TE, 4 WR" is the highest with 5.2 yards 
per play and produces 0.7 yards more than the next highest formation on 
average. 

The **defensive personnel** with the most yards, is the "4 DL, 2 LB, 5 DB" 
formation. Again, this occurs because it is the most common. Looking at the 
average yards per personnel, "1 DL, 4 LB, 6 DB" is the highest with 5.7 yards 
per play and produces 0.5 yards more than the next highest formation on 
average. 

### How well can we predict the yardage for a running play?
Using the explained variance as our performance metric, we can't predict the 
yardage from a running play well when using tree based models such as 
decision trees and random forests. 

Here is the explained variance on the validation dataset for each model:  
* Decision tree with default parameters: -0.984
* Decision tree with optimized parameters: -0.004
* Random forest with optimized parameters: 0.019

The random forest model performed the best on the validation set but the 
explained variance was still very low. When evaluating the model on the test 
dataset, we see the explained variance is still low at 0.018

### What are the most important features that influence the prediction for a running play?
Top most important features from the random forest model:
* Yard line
* X-coordinate
* Y-coordinate
* Player weight
* Temperature

![Feature Importance Graph]()

A full summary of the results can be found in both the notebooks mentioned above 
and in the following 
[blogpost](https://medium.com/@jonathan.m.novak/why-replacing-nfl-coaches-with-ai-is-not-so-simple-abbc101daf0c).

# Acknowledgments
* [NFL Big Data Bowl](https://operations.nfl.com/gameday/analytics/big-data-bowl/)
* [Kaggle](https://www.kaggle.com/c/nfl-big-data-bowl-2020/overview)
* [scikit-learn](https://scikit-learn.org/stable/index.html)
* [pandas](https://pandas.pydata.org/)
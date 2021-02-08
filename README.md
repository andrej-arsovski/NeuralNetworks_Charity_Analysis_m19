# Predicting Funding Applications Using Deep Neural Networks

## Overview

A large company funds thousands of organizations every year. The funding organization wants a way to choose organizations that will go on to be successful if funded. Here we have a robust data set that contains information from 34,000 organizations and it includes metadata such as:

EIN and NAME—Identification columns; APPLICATION_TYPE—Alphabet Soup application type; AFFILIATION—Affiliated sector of industry; CLASSIFICATION—Government organization classification; USE_CASE—Use case for funding; ORGANIZATION—Organization type; STATUS—Active status; INCOME_AMT—Income classification; SPECIAL_CONSIDERATIONS—Special consideration for application; ASK_AMT—Funding amount requested; IS_SUCCESSFUL—Was the money used effectively



The objective of this work is to use this information to create a binary classifier that is capable of predicting whether applicants will be successful if funded by the large company.

## Results

### Data Processing

model target: The target of the model was the IS_SUCCESSFUL column. This binary column informs us whether the funding was used effectively. Our model will use portions from the rest of the data to predict this value in future candidates.

model features: The model uses data from the APPLICATION_TYPE, AFFILIATION,CLASSIFICATION, USE-CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT columns in order to predict the target value. These are the model's "features".

disregarded data: Information contained in the EIN, and NAME columns was determined to not be informative for the model and thus not used in the features set.

### Compiling, Training, and Evaluating the Model

The model architecture was sequential, using 39 input features, and 4 hidden layers. The first layer had 80 nodes, the second 30, the third had 10 and the output had a single output using "sigmoid" activation. The model was found to perform best when the first 3 layers all used the "relu" activation. This was determined largely by trial and error.

![model_optimized.png](https://github.com/andrej-arsovski/NeuralNetworks_Charity_Analysis_m19/blob/main/screenshots/model_optimized.png)

The final optimized model was not able to exceed the 75% benchmark.

A number of spets were attempted in order to increase the accuracy of the model to no avail:

1. The number of layers from 1 to 4 were tried with no improvement in performance.
2. The "ASK_AMT" was edited to eliminate outlying points since the vast majority asked for 5000. Finally this column was dropped from the features set since effectively all ask amounts were the same value.
3. Various activation functions were attempted in the hidden layers such as "sigmoid", "tanh", and "relu" with marginal changes in performance.
4. Epoch values of of 50, 100 did not show significant difference in performance.

## Summary

The final version of the model had a prediction accuracy of 72.5% and loss of 0.56

![model_performance.png](https://github.com/andrej-arsovski/NeuralNetworks_Charity_Analysis_m19/blob/main/screenshots/model_performance.png)

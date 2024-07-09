# Module 21 Challenge
# Neural Network Model Report

## Overview of the Analysis
In this challenge, a dataset of more than 34,000 organizations that have received funding from Alphabet Soup over the years has been provided, where the dataset includes columns comprised of: 

* (1) EIN and NAME: Identification columns;
* (2) APPLICATION_TYPE: Alphabet Soup application type;
* (3) AFFILICATION: Affiliated sector of industry;
* (4) CLASSIFICATION: Government organization classification;
* (5) USE_CASE: Use case for funding;
* (6) ORGANIZATION: Organization type;
* (7) STATUS: Active Status;
* (8) INCOME_AMT: Income classification;
* (9) SPECIAL_CONSIDERATIONS: Special considerations for application;
* (10) ASK_AMT: Funding amount requested; and
* (11) IS_SUCCESSFUL: Was the money used effectively.

Using the dataset, a binary classifier has been created to predict whether applicants will be successful if funded by Alphabet Soup.

### Results of the Analysis
* Data Preprocessing
  * The following was identified as the target variable for both the initial and optimized models: IS_SUCCESSFUL.

  * Initial Model:
    * The following were identified as the feature variables: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT.
    * The EIN and NAME variables were dropped.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/initial_drop_EIN_and_NAME.png)
  

  * Optimized Model:
    * The following were identified as the feature variables: NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT.
    * Only the EIN variable was dropped.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/optimization_drop_EIN_only.png)

* Compiling, Training, and Evaluating
  * As provided in the Starter_Code of this Challenge, two hidden layers were employed for initial model; this remained unchanged for the optimized model.
  * The two hidden layers of both models employed a "relu" activation function for efficient and relatively simple computations. (Ref: https://www.bing.com/search?q=relu+and+sigmoid+functions&qs=n&form=QBRE&sp=-1&ghc=1&lq=0&pq=relu+and+sigmoid+functions&sc=11-26&sk=&cvid=ABD8A7536AB143C5BAA17DEFF5DCEF0B&ghsh=0&ghacc=0&ghpl=)
 * The output layers of both models employed a "sigmoid" activation function for its suitability in tasks like binary classification. (Id.)


  * Initial Model:
    * As provided in the Starter_Code of this Challenge, the first and second hidden layers comprised 80 and 30 neurons, respectively.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/initial_nodes.png)
  

  * Optimized Model:
    * As instructed, differing values of neurons were repeatedly examined in both the first and second hidden layers in successive attempts to achieve a target predictive accuracy of higher than 75%.
    * Favorable results were obtained when the first and second hidden layers comprised merely 8 and 3 neurons, respectively.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/optimization_nodes.png)

  * Initial Model:
    * Target accuracy achieved 72.65%.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/initial_accuracy.png)
  

  * Optimized Model:
    * Target accuracy achieved 76.97%, thereby exceeding a target predictive accuracy of 75%.

    ![image](https://github.com/jimlhaugen/deep-learning-challenge/blob/master/Screenshots/optimization_accuracy.png)

    * The steps taken to achieve the target accuracy of higher than 75% included varying the configurations of the initial model in multiple examinations by (1) creating more bins, (3) increasing and decreasing the number of values for each bin, (4) adding hidden layers, and (5) addingor reducing the number of epochs.  None of these configurations produced a favorable result of achieving a target predictive accuracy of higher than 75%.  In fact, a majority of the configurations led to poorer results than the results obtained with the initial model.
    * As shown above, the steps taken to achieve the target accuracy included (1) including the NAME variable and (2) reducing the number of neurons in both first and second layers.  Despite the numerous attempts of varying at least three model configuration factors of the inital model, a target predictive accuracy of higher than 75% was not achieved. 

### Summary
The iniital deep learning model was unable to exceed a predictive accuracy of higher than 75%.  Even after changing the configuration of the model by changing numerous factors, the occurance of exceeding 75% was only achieved once.  This is disappointing and suggests that the initial model is unsuitable for classification problem.  Rather, a Logistic Regression Model with a RandomOverSampler module would likely produce a more favorable accuracy based upon results achieved in preceding Challenge 20 with a dataset of similar varaibles.
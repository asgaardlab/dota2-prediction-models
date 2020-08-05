## Building and evaluating victory prediction models for Dota 2

This notebook contains instructions on how to run the scripts to build and evaluate prediction models for team victory in Dota 2.

For more details on how we performed the data preparation and extracted the model features, please check our [Dota 2 paper](https://markosviggiato.github.io/resources/Markos_AIIDE_20.pdf).

**Important note:** For reproducibility purposes, to run this code with the same dataset that we used, **you should download the readily-available model features**, which can be obtained from the *model_pre_match_features.zip* file, available [here](http://doi.org/10.5281/zenodo.3890315).


---

## Dependencies

The following dependencies are required to build and evaluate the prediction models (if you are running the scripts on a local machine):

 - Python 3.7
 
 
 - Git 2.20.1.windows.1
  
  
 - [Numpy 1.18.4](https://numpy.org/)

    `
    pip install numpy
    `


 - [Pandas 0.24.2](https://pandas.pydata.org/)
 
    `
    pip install pandas
    `
 
 
 - [scikit-learn 0.20.3](https://scikit-learn.org/stable/)

    `
    pip install scikit-learn
    `


 - [xgboost 1.1.0](https://xgboost.readthedocs.io/en/latest/)

    `
    pip install xgboost
    `
    
 ## Structure of directories
 
 The following directories contains the scripts of each used algorithm.

 - 1 - XGBoost: contains the scripts to read the model features, build and evaluate xgboost models
 - 2 - Random Forest: contains the scripts to read the model features, build and evaluate random forest models
 - 3 - Logistic Regression: contains the scripts to read the model features, build and evaluate logistic regression models

Be aware that, for each algorithm, there are 3 different scripts, one for each data group we adopted in our study: regular matches, time blowout matches, and score blowout matches. You should use the model features of each dataset separately.

The features for each type of match can be obtained from the *model_pre_match_features.zip* file, available for download in this repository.

## Before running the scripts

Before running the scripts, note that each directory contains three different scritps for the related algorithm, each script being for a different type of Dota 2 match (as indicated by the name of the script). 

In the **1 - XGBoost** directory:

*   **xgboost-regular.ipynb** contains the script for the regular matches
*   **xgboost-score_blowout.ipynb** contains the scripts for the score blowout matches
*   **xgboost-time_blowout.ipynb** contains the script for the time blowout matches

In the **2 - Random Forest** directory:

*   **random_forest-regular.ipynb** contains the script for the regular matches
*   **random_forest-score_blowout.ipynb** contains the scripts for the score blowout matches
*   **random_forest-time_blowout.ipynb** contains the script for the time blowout matches
   
In the **3 - Logistic Regression** directory:

*   **logistic_regression-regular.ipynb** contains the script for the regular matches
*   **logistic_regression-score_blowout.ipynb** contains the scripts for the score blowout matches
*   **logistic_regression-time_blowout.ipynb** contains the script for the time blowout matches

## Step-by-step to run the scritps

1.   Download the model features from [this zenodo repository](http://doi.org/10.5281/zenodo.3890315). The features for each of the three types of matches are available in the *model_pre_match_features.zip* file.

2.   Extract the contents from the *model_pre_match_features.zip* file and keep the structure and names of its sub-directories and respective files.

3.  Place the model features files that you extracted on the following locations depending on where you are running this code.


 *   Running on a local machine:

     Place the *model_pre_match_features* directory at the same level as this instructional notebook (i.e., one level above of the directories with the scripts for each algorithm). In this case, you will need to uncomment the lines of code where the data is read (this will be indicated in the code).

     Note that you are free to change the location of the model feature directory and sub-directories as long as you properly adjust the references to those locations in the code (this will also be indicated in the code).


 *   Running on Google Colab:

     Upload the model features to the Google Colab session according to the type of match you are using. If you want to run the scrips for the regular matches (either XGBoost, Random Forest, or Logistic Regression), please upload the *dota2_regular-new_features.csv* feature file. If you want to run the scripts for the score blowout matches, upload the *dota2_score_blowout_features.csv* feature file. If you want to run the scripts for the time blowout matches, upload the *dota2_time_blowout_features.csv* feature file. 

     You should use the upload button, located at the Google Colab menu on the top left (note that the notebook must connect to a runtime for you to be able to manage files):

     ![Upload button](https://drive.google.com/uc?export=view&id=1_yDESFJnEOBTd4LQZ9PQV1d_kkRM6Ma3)

     Note that you will only need to upload the files to the notebook that contains the script you want to run. In the beginning of the notebook with the script, there is an indication of which file(s) you need to upload to that notebook. Also note that, if you close the notebook (i.e., the Google Colab session), you will need to re-upload the file(s).


4.   Run the notebook with the script

## General Questions

If you have any question or suggestion, please contact the repository owner at markosviggiato[at]gmail.com

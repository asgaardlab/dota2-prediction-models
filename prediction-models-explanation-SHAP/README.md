## Feature importance to explain victory predictions for Dota 2

This notebook contains instructions on how to run the script to apply the [SHAP values](http://papers.nips.cc/paper/7062-a-unified-approach-to-interpreting-model-predictions.pdf) technique to explain victory predictions for Dota 2 matches. We apply SHAP values to the predictions made by out XGBoost models, which are implemented together with the SHAP technique.

For more details on how we performed the data preparation, extracted the model features, and adapted the SHAP technique for our data, please check our [Dota 2 paper](https://markosviggiato.github.io/resources/Markos_AIIDE_20.pdf).


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
  
  
 - [matplotlib 3.0.2](https://matplotlib.org/)

    `
    pip install matplotlib
    `
    
    
 - [shap 0.35.0](https://github.com/slundberg/shap)

    `
    pip install shap
    `
    
 ## Structure of directories
 
 In this directory, you will find the following sub-directories with corresponding contents:

 - XGBoost: contains the scripts to read the model features, build and evaluate XGBoost models along with the scripts to apply the SHAP technique to the prediction made by the XGBoost model. Be aware that the scripts for all the three types of matches (regular matches, time blowout matches, and score blowout matches) are in the same notebook: *SHAP_values_xgboost_colab.ipynb*
 
   You should use the model features of each dataset (obtained from the file *model_pre_match_features.zip*) separately.

 - SHAP_plots: contains the generated SHAP plots (summary plots and barplots)
 
 ## Before running the script
 
  **Important note:** the scripts used in this part of the work were run on [Google colab](https://colab.research.google.com/notebooks/welcome.ipynb), where you do not need
  to install all the dependencies (only the *shap* library). Note that some steps are slighty different compared to running the scripts on a local machine
  (e.g., the functions to read the data rely on the data uploaded to the google colab session). If you desire to run the scripts locally on your machine, you need to
  install the dependencies (link above).
  
## Step-by-step to run the script

1.   Download the model features from [this zenodo repository](http://doi.org/10.5281/zenodo.3890315). The features for each of the three types of matches are available in the *model_pre_match_features.zip* file.

2.   Extract the contents from the *model_pre_match_features.zip* file and keep the structure and names of its sub-directories and respective files.

3.  Place the model features files that you extracted on the following locations depending on where you are running this code.


  *   Running on a local machine:

      Place the *model_pre_match_features* directory at the same level as this instructional notebook (i.e., one level above of the directories with the scripts for each algorithm). In this case, you will need to uncomment the lines of code where the data is read (this will be indicated in the code).

      Note that you are free to change the location of the model feature directory and sub-directories as long as you properly adjust the references to those locations in the code (this will also be indicated in the code).


  *   Running on Google Colab:

      Upload the all the three model feature files to the Google Colab session. The *path_to_features* variable is already properly adjusted to read the feature files uploaded to Google Colab.

      You should use the upload button, located at the Google Colab menu on the top left (note that the notebook must connect to a runtime for you to be able to manage files):

      ![Upload button](https://drive.google.com/uc?export=view&id=1_yDESFJnEOBTd4LQZ9PQV1d_kkRM6Ma3)

      Note that you will only need to upload the files to the notebook that contains the script you want to run. In the beginning of the notebook with the script, there is an indication of which file(s) you need to upload to that notebook. Also note that, if you close the notebook (i.e., the Google Colab session), you will need to re-upload the file(s).

4.   Run the notebook with the script

**Important notes:**

This script contains the XGBoost implementation we used in the paper, which is the model we use to apply the SHAP values.

We perform a grid search to tune the hyperparameters of the XGBoost model. The grid of values that we use can be adjusted to incorporate more values.

Finally, the script to apply the SHAP technique generates two types of plots (summary plots and barplots), which will be available for download in the Google Colab session. Feel free to save those plots in a location that you desire.


## General Questions

If you have any question or suggestion, please contact the repository owner at markosviggiato[at]gmail.com

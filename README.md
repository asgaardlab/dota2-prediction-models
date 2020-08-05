## General instructions on how to build and evaluate victory prediction models for Dota 2

<a href="https://blog.dota2.com/" target="_blank"><img src="https://live.staticflickr.com/3/31426543551_75acf3a4f9_b.jpg" alt="Dota 2 game" title="Dota 2 game" width=225 height=125></a>


This notebook contains general instructions on how to run the scripts to build, evaluate, and explain prediction models for team victory in the Dota 2 game.


For more details on how we performed the data preparation and extracted the model features, please check our Dota 2 paper: <a href="https://markosviggiato.github.io/resources/Markos_AIIDE_20.pdf" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/8/87/PDF_file_icon.svg" alt="Dota 2 paper" title="Dota 2 paper" width=25 height=25></a>

The used dataset is available in the following zenodo repository: <a href="http://doi.org/10.5281/zenodo.3890315" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/8/86/Database-icon.svg" alt="Dota 2 dataset" title="Dota 2 dataset" width=25 height=25></a>



---


## Dependencies

The following dependencies are required to run the scripts on your local machine (you do not need to locally install them if you are running the scripts on cloud services like Google Colab):

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
 
 The following directories contains the scripts to build the prediction models. 


 - *prediction-models*: contains the scripts to read the model features, build and evaluate prediction models using three algorithms: XGBoost, Random Forest, and Logistic Regression. Note that, for each algorithm, there are 3 different scripts, one for each data group we adopted in our study: regular matches, time blowout matches, and score blowout matches.
 
 - *prediction-models-explanation-SHAP*: contains the scripts to apply the SHAP values technique to explain victory predictions for Dota 2 matches.
 
 ## Dataset
 
 In order to run the scripts within the *prediction-models* and the *prediction-models-explanation-SHAP* directories, you will need to first download the dataset (model features), which is available [here](http://doi.org/10.5281/zenodo.3890315).

The features are available in the *model_pre_match_features.zip* file. Please download this zip file and extract its contents.

If you desire to run the scripts on Google Colab, you will need to upload all the three feature files to your Google Colab session (the detailed instructions on how to upload the files are in the *prediction-models* and *prediction-models-explanation-SHAP* directories).

## Running the scripts

For detailed instructions on how to the scripts, please look at the *prediction-models* and the *prediction-models-explanation-SHAP* directories, as they contain the necessary information regarding the scripts.

Be aware that the scripts in the *prediction-models* directory (to build and evaluate the predicion models) and in the *prediction-models-explanation-SHAP* directory (to build and explain the XGBoost model) should be run in Google Colab by default. The few changes necessary to run the scripts on a local machine are explained in the specific notebooks with the instructions.

## General Questions

If you have any question or suggestion, please contact the repository owner at markosviggiato[at]gmail.com

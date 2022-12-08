# To loan or not to loan - that is the question

The project was devolped using python and jupyter notebooks for data analysis, data preparation, feature selection and the resolution of the predictive problem. The tool Rapid Miner was used especially for the descriptive problem.

Even so, the Rapid Miner was also explored in order to make predictions and add more data preparation parallel to notebooks, however it was not fully optimized and taken into account after compared with the notebooks pipeline.

## Python and Jupyter Notebooks

The project is composed by 7 jupyter notebooks:
- **data_analysis.ipynb**
    - This notebook is the one responsible to analyse the data, the original one, the processed data in some cases and the Final table data
    - The notebook is organized by data table and at the end have an "Integrated Data" section that corresponds to the Final table analysis
    - A boolean constant "DISPLAY_PAIRPLOTS" can be changed according to the desire of displaying some pair plots
    - A boolean constant "SELECTED" can be changed to choose the data to be used in PCA and/or in correlation map (True -> data selected previously by feature selection; False -> data joined into the Final Table)
- **data_preparation.ipynb**
    - This notebook is the one responsible to process the original data and save each processed table in files. 
    - The notebook use the processed tables to join them into a single table and save it in a file (data.csv or data_comp.csv).
    - After, it encodes the final data and saves it in a file (enc_data.csv or enc_data_comp.csv)
    - At the begining of the notebook there is a boolean constant "DEV" that indicates if the data processing should be done to the dev data (original data files with sufix '_dev') or to the comp data (data gethered from the kaggle (competition data))
- **feature_selection.ipynb**
    - This notebook is the one responsible to select the features to later be used in the prediction phase
    - There is a boolean constant "SELECT_WRAPPED" that indicates if the wrappers should be used to seelct the data or only the filter and manually selected are expected
    - There is a boolean constant "REMOVE_HIGH_CORRELATED" that indicates if the high correlated features (>85%) should be removed or not
    - The 3 wrapper methods are executed and then compared to select the features used in the best result
    - A file data_selected.csv will be saved with the enc_data.csv data, but with the features selected
- **predictions_dev.ipynb**
    - This notebook is the one responsible to train several models using hardcoded parameters and evaluate them using an hold-out strategy
    - A boolean constant "SMOTE" allows to choose if the smote technique should be used to balance the data or not in the train split
    - There is a general function "add_model" that receives the classifier, apply changes (smote and/or scaling), train it and save it as well as other metrics in dictionary
    - The test split (and the train split for overfit analysis) is used to make predictions for each model
    - The models keeped in the dictionary "results" are evaluated usin accuracy, precision, recall, f1 and roc_auc, and the confusion matrix and roc curve is displayed
    - A piece of the final "result" structure is represented below
```
results = {
    dtc: {
        model: ...,
        X_train: ...,
        X_test: ...,
        y_train: ...,
        y_test: ...,
        fit_time: ...,
        test_pred: ...,
        train_pred: ...,
        test_pred_prob: ...,
        train_pred_prob: ...
    },
    rf: {
        ...
    }
}
```
- **predictions_dev_cv.ipynb**
    - This notebook is the one responsible to use cross validation to evaluate the models predictions
    - The data (all or selected according to "ALL_DATA") is evaluated, for several models, using the cross validation technique with a 3 Repeats Stratified 5 fold
    - "USE_SMOTE" allows to choose if smote should be used or not
    - At the end, the scores of the 15 (3*5) evaluations for each model are repreented in a boxplot
- **predictions_dev_gs.ipynb**
    - This notebook is the one responsible to make the parameter tunning for the several models
    - The data is held-out and the grid search is applied to the train split. The best parameters will be chosen according to the AUC of a 3 Repeated Stratified 5 fold Cross-validation
    - The best parameters for each model and its score is saved in a file under the directory 'grid_search_results/'. The filename contains a timestamp so it can not be replaced on other execution of the notebook
- **predictions_comp.ipynb**
    - This notebook is the one responsible to train the models using all the dev data and predict the competition targets
    - The model predictions to be saved are hardcoded chose
    - A file ready to be submited in kaggle is saved in 'kaggle/submission.csv'


## Rapid Miner

**TODO**
Descriptive Problem
- Process used is in path `./RapidMiner/processes/Clustering/All_Data_Clustering.rmp
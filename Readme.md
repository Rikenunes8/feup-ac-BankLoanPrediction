# To loan or not to loan - that is the question

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

Descriptive Problem
- Process used is in path `./RapidMiner/processes/Clustering/All_Data_Clustering.rmp
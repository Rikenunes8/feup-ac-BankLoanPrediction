Notes:\
- What has a higher cost, issuing a loan to someone who won't pay or not issuing a loan to someone who **would** pay? 

# Data Mining Project - Banking Loans

## Business Understanding

### Analysis of requirements

The banks would like to have the possibility to guess with an high level of certainty if accepting a loan requested by a customer would be positive for the bank. The banks keep a lot of data about their customers, including their personal information and the actions they already take in the bank. For this reason, the banks hope this data to be enough to correctly accept or not the customer's loan.

#### Descriptive problem:
(change) Identify groups of costumer that represent relevant behaviors for the bank.

#### Predictive Problem:
The goal is to predict whether or not a given costumer will default. This is a **classification** problem and the predicted value is either 1 (the costumer will default) or -1 (the costumer will pay).



### Definition of business goals


On banking loans world, banks would like to know when to accept a loan or not so they can increase gains and decrease losses. By analyzing customers, banks can draw conclusions about their customer's ability to keep their part of the deal. These conclusions may or may not be 100% correct, however the goal is to make profit by accepting loans only from costumers that are expected to pay (with some margin of error). 

Our business goals are as follows:
- Reduce defaulting significantly:
    - Issuing 0 loans (that get paid) represents a loss for the bank (since the bank has expenses to pay), therefore it is not an option.
    - Reduce defaulting by 70% (true positive rate at least 70%). 

- Do not significantly reduce credit to good costumer:
    - Give credit to at least 90% of the good costumer (true negative rate above 90%)


### Data mining goals

According to business goals there are data mining goals that can be set. We can understand that the priority for the costumer (the bank) is to decrease the amount of loans that result in default. 

<!-- We define our confidence level (or threshold) at 80%, which means that it needs to be at least 80% sure that a costumer will pay in order to output 1. -->

<!--So that we can define a greater confidence interval at which loans should be accepted, let's say 80%. If the model is not at least 80% sure that the customer will pay the loan than the bank should refuse the loan. -->

<!-- With this strategy, it's hope to have the **precision** measure greater than the **recall** measure to fulfill the bank expectations about not accepting fallible loans. -->

The positive case is where the costumer defaults, so we want the ROC curve of our model, for a certain threshold, to be in the area defined by the conditions:. 
TPR > 0.70
FPR < 0.10

<!--According to business goals there data mining goals that can be set. We can understand that the priroty for the banks is to increase the ammount of loans rejected correctly. So that we can define a greater confidence interval at which loans should be accepted, let's say 80%. If the model is not at least 80% sure that the customer will pay the loan than the bank should refuse the loan. With this strategy, it's hope to have the **precision** measure greater than the **reacall** measure to fulfill the bank expectations about not accepting fallible loans.-->


**TODO: Each topic is evaluated from 0 to 6. Let's try to get 4 or 5 for each of them. Only mark as done when you think this goal is accomplished.**

## Data Understanding
- [ ] diversity of statistical methods - **rich and justified**
    - [X] Mean of each column
        - Every numerical target
    - [X] Median and Quartiles
        - Every numerical target
    - [X] Frequency
        - Every categorcal target
    - [X] Correalation
        - All features in Data
    - [X] Mode
        - Operation for each type in Transactions
    - [ ] Range
    - [ ] Standard Deviation (analysed)
- [ ] complexity of statistical methods
    - [X] Group by attributes means
    - [ ] Contigency table
    - [ ] Correaltion
        - [ ] Pearson
        - [ ] Spearman
- [ ] interpretation of results of statistical methods
    - District name can be seen like an id so it's not important
    - k_symbol, bank, account features in transaction table have many null values, so we may consider remove it.
    - **TODO** more interpretations
- [ ] knowledge extraction from results of statistical methods
    - The clients whose loan has status 1 have a greater monthly income than the ones whose status is -1 in median
    - **TODO** more knowledge extraction
- [ ] diversity of plots  -  Justifiy
    - [X] Bar plot
    - [X] Histogram
    - [X] Box plot
    - [X] Bar plot 2D dodge
    - [X] Scatter plot 3D
        - **TODO** linear regression for each target
    - [X] Heat map
    - [ ] QQ plot
- [ ] complexity of plots  -  3D with clean results
    - [ ] Grouped data box plots in same plot
    - [ ] Scatter plot with clear results
    - [ ] Scatter plot PCA
- [ ] presentation
    - **TODO** Split analysis by tables maybe
- [X] interpretation of plots
- [ ] visual knowledge extraction  -  interesting, novel and non-trivial knowledge obtained

## Data preparation
- [X] data integration
    - join important features of each table in Data
- [ ] assessment of dimensions of data quality  -  **6 diumensions**
- [ ] (cleaning): redundancy  -  **systematic removal of attributes**
    - **TODO** remove attributes with correaltion above 70% (?)
- [ ] (cleaning): missing data  -  **replace MVs with complex method (e.g. regression, classification) with correct experimental setup**
    - [X] Replace MVs with simple method 
- [ ] (cleaning): outliers  -  **identify and discuss outliers, and address them with simple approach**
- [ ] data transformation for compatibility with algorithms  -  **adequate complex discretization or rescaling**
    - [X] Discretization 
    - [X] Normalization (aka rescaling)
- [ ] feature engineering from tabular data  -  **complex methods (e.g. aggregation) AND knowledge (e.g. business concepts)**
    - [X] Aggregation of transactions according to business concept of monthly income
    - [ ] **TODO more**
- [ ] sampling for domain-specific purposes  -  **focus on adequate subset of the population**
- [ ] sampling for development  -  **start with very small sample and grow to significant one**
- [ ] imbalanced data  -  **used advanced methods (e.g. SMOTE) correctly**
    - [ ] Apply SMOTE on training dataset after spliting the data 
- [ ] feature selection  -  **correct, combined use of filter and wrapper-based methods**
    - [ ] Filter
    - [ ] Wrap

## Descriptive
- [ ] diversity of algorithms  -  **tested 3+ with significantly different language bias OR with a significant number of variants**
    - [X] Decision Tree
    - [X] Random Foreest
    - [X] Support Vector Machine
    - [ ] Neural Network
    - [ ] Nearest Neighbour
    - [ ] Naive Bayes
- [ ] parameter tuning  -  **systematic approach**
    - [ ] Grid search
    - [ ] Random Search
    - [ ] Evaluation Methodology with hiperparameter tunning
- [ ] understanding algorithm behavior  - **algorithm and parameters**
- [ ] performance measure  -  **focus on performance measure(s) aligned with DM goals and data characteristics**
    - [X] ROC curve
    - [X] AUC
- [ ] correct interpretation of performance measures
- [ ] comparative analysis of results
- [ ] model improvement
- [ ] analysis of results

## Predictive
- [X] diversity of tasks  -  **classification**
- [ ] diversity of algorithms
- [ ] parameter tuning
- [ ] understanding algorithm behavior
- [ ] (performance estimation) training vs test
    - [X] Test split evaluation
    - [ ] Training split evaluation
    - [ ] Compare Test vs Training
- [ ] (perfomance estimation): other factors (e.g. time)  -  **additional factors correctly taken into account**
- [ ] (performance estimation): perfomance measure
    - [X] ROC curve
    - [X] AUC
- [ ] (performance estimation): correct interpretation of performance measures
    - [ ] Interpret precision and recall
    - [ ] Interpret AUC
- [ ] (performance estimation): analysis of results
- [ ] model improvement
- [ ] feature importance
- [ ] analysis of "white-box" models

## Project Management
- [ ] methodology  -  **a methodology was followed carefully, reflecting on the documentation produced**
    - [X] Crisp was followed
    - [ ] Document
- [ ] plan  -  **a detailed plan was created and it guided the development**
- [ ] PM tools  -  **detailed task sharing, supported by appropriate management tool**
- [ ] collaboration tools

## Tools
- [ ] analytics  -  **multiple tools, from the ones presented in the courses**
    - [X] Python
    - [ ] Rapid Miner
- [ ] database
- [ ] other tools (e.g. data cleaning, visualization)  -  **limited but correct use of other tools**

## Presentation
- [ ] quality of layout
- [ ] quality of content in slides
- [ ] delivery
- [ ] use of time

Notes:\
- What has a higher cost, issuing a loan to someone who won't pay or not issuing a loan to someone who **would** pay? 

# Data Mining Project - Banking Loans

## Business Understanding

### Analysis of requirements

The banks would like to have the possibility to guess with an high level of certainty if accepting a loan requested by a customer would be positive for the bank. The banks keep a lot of data about their customers, including their personal information and the actions they already take in the bank. For this reason, the banks hope this data to be enough to correctly accept or not the customer's loan.

### Descriptive problem:
(change) Identify groups of clients that represent relevant behaviors for the bank.

### Predictive Problem:
The goal is to predict whether or not a given client will default. This is a **classification** problem and the predicted value is either 1 (the costumer will pay) or -1 (the costumer will default).



### Definition of business goals


On banking loans world, banks would like to know when to accept a loan or not so they can increase gains and decrease losses. By analyzing customers, banks can draw conclusions about their customer's ability to keep their part of the deal. These conclusions may or may not be 100% correct, however the goal is to make profit by accepting loans only from costumers that are expected to pay (with some margin of error). 

The positive case is where the client pays and our business goals are as follows:
- Reduce defaulting significantly:
    - Issuing 0 loans (that get paid) represents a loss for the bank (since the bank has expenses to pay), therefore it is not an option.
    - Reduce defaulting by 70% (true negative rate at least 70%). 

- Do not significantly reduce credit to good clients:
    - Give credit to at least 90% of the good clients (true positive rate above 90%)


### Data mining goals

According to business goals there are data mining goals that can be set. We can understand that the priority for the client (the bank) is to decrease the amount of loans that result in default. We define our confidence level (or threshold) at 80%, which means that it needs to be at least 80% sure that a costumer will pay in order to output 1.

<!--So that we can define a greater confidence interval at which loans should be accepted, let's say 80%. If the model is not at least 80% sure that the customer will pay the loan than the bank should refuse the loan. -->

<!-- With this strategy, it's hope to have the **precision** measure greater than the **recall** measure to fulfill the bank expectations about not accepting fallible loans. -->

TPR > 0.90
TNR > 0.70

This means that the ROC curve of our model should, for a certain threshold, be in the area defined by the above condition.




## Data Understanding

### Statistical Methods Diversity and Complexity

- Mean
- Median and Quartiles
- Frequency
- Correlation

### Interpretation of results of statistical methods

### Knowledge extraction from results of statistical methods

### Plots Diversity and Complexity

- Bar plot
- Histogram
- Box plot
- Bar plot 2D dodge
- Scatter plot 3D
- Heat map

DU: presentation
DU: interpretation of plots
DU: visual knowledge extraction

DP: data integration
DP: assessment of dimensions of data quality
DP (cleaning): redundancy
DP (cleaning): missing data
DP (cleaning): outliers
DP: data transformation for compatibility with algorithms
DP: feature engineering from tabular data
DP: sampling for domain-specific purposes
DP: sampling for development
DP: imbalanced data
DP: feature selection

descriptive: diversity of algorithms
descriptive: parameter tuning
descriptive: understanding algorithm behavior
descriptive: performance measure
descriptive: correct interpretation of performance measures
descriptive: comparative analysis of results
descriptive: model improvement
descriptive: analysis of results

predictive: diversity of tasks
predictive: diversity of algorithms
predictive: parameter tuning
predictive: understanding algorithm behavior
predictive (performance estimation) training vs test
preditive (perfomance estimation): other factors (e.g. time)
predictive (performance estimation): perfomance measure
predictive (performance estimation): correct interpretation of performance measures
predictive (performance estimation): analysis of results
predictive: model improvement
predictive: feature importance
predictive: analysis of "white-box" models

project management: methodology
project management: plan
project management: PM tools
project management tools: collaboration tools

tools: analytics
tools: database
tools: other tools (e.g. data cleaning, visualization)

presentation: quality of layout
presentation: quality of content in slides
presentation: delivery
presentation: use of time

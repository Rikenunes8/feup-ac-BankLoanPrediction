Notes:\
- What has a higher cost, issuing a loan to someone who won't pay or not issuing a loan to someone who **would** pay? 

# Data Mining Project - Banking Loans

## Business Understanding

### Analysis of requirements

The banks would like to have the possibility to guess with an high level of certainty if accepting a loan requested by a customer would be positive for the bank. The banks keep a lot of data about their customers, including their personal information and the actions they already take in the bank. For this reason, the banks hope this data to be enough to correctly accept or not the customer's loan.

#### Descriptive problem:
(change) Identify groups of costumer that represent relevant behaviors for the bank.

#### Predictive Problem:
The goal is to predict whether or not a given costumer will default. This is a **binary classification** problem and the predicted value is either -1 (the costumer will default) or 1 (the costumer will pay).



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

The positive case is where the costumer defaults, so we want the ROC curve of our model, for a certain threshold, to be in the area defined by the conditions:
- TPR > 0.70
- FPR < 0.10

<!--According to business goals there data mining goals that can be set. We can understand that the priroty for the banks is to increase the ammount of loans rejected correctly. So that we can define a greater confidence interval at which loans should be accepted, let's say 80%. If the model is not at least 80% sure that the customer will pay the loan than the bank should refuse the loan. With this strategy, it's hope to have the **precision** measure greater than the **reacall** measure to fulfill the bank expectations about not accepting fallible loans.-->

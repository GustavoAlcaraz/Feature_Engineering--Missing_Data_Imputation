# Rare Labels

## Labels that occur rarely

Categorical variables are those which values are selected from a group of categories, also called labels. Different labels appear in  
the dataset with different frequencies. Some categories appear a lot in the dataset, whereas some other categories appear only in a few 
number of observations.

For example, in a dataset with information about loan applicants where one of the variables is "city" where the applicant lives, cities 
like 'New York' may appear a lot in the data because New York has a huge population, whereas smaller towns like 'Leavenworth' will appear
 only on a few occasions (population < 2000 people), because the population there is very small. A borrower is more likely to live in New York, 
because far more people live in New York.

In fact, categorical variables often contain a few dominant labels that account for the majority of the observations and a large number of 
labels that appear only seldom.


### Are Rare Labels in a categorical variable a problem?

Rare values can add a lot of information or none at all. For example, consider a stockholder meeting where each person can vote in 
proportion to their number of shares. One of the shareholders owns 50% of the stock, and the other 999 shareholders own the remaining 50%. 

The outcome of the vote is largely influenced by the shareholder who holds the majority of the stock. The remaining shareholders may have an 
impact collectively, but they have almost no impact individually.  

The same occurs in real life datasets. The label that is over-represented in the dataset tends to dominate the outcome, and those that are 
under-represented may have no impact individually, but could have an impact if considered collectively.

More specifically,

- Rare values in categorical variables tend to cause over-fitting, particularly in tree based methods.

- A big number of infrequent labels adds noise, with little information, therefore causing over-fitting.

- Rare labels may be present in training set, but not in test set, therefore causing over-fitting to the train set.

- Rare labels may appear in the test set, and not in the train set. Thus, the machine learning model will not know how to evaluate it. 


**Note** Sometimes rare values, are indeed important. For example, if we are building a model to predict fraudulent loan applications, 
which are by nature rare, then a rare value in a certain variable, may be indeed very predictive. This rare value could be telling us 
that the observation is most likely a fraudulent application, and therefore we would choose not to ignore it.
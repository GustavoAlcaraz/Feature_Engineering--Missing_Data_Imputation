## Adding a variable to capture NA

In previous notebooks we learnt how to replace missing values by the mean, median or by extracting a random value. 
In other words we learnt about mean / median and random sample imputation. These methods assume that the data are 
missing completely at random (MCAR).

There are other methods that can be used when values are not missing at random, for example arbitrary value 
imputation or end of distribution imputation. However, these imputation techniques will affect the variable 
distribution dramatically, and are therefore not suitable for linear models.

**So what can we do if data are not MCAR and we want to use linear models?**

If data are not missing at random, it is a good idea to replace missing observations by 
the mean / median / mode AND  **flag** those missing observations as well with a **Missing Indicator**. 
A Missing Indicator is an additional binary variable, which indicates whether the data was missing for 
an observation (1) or not (0).


### For which variables can I add a missing indicator?

We can add a missing indicator to both numerical and categorical variables. 

#### Note

Adding a missing indicator is never used alone. On the contrary, it is always used together with 
another imputation technique, which can be mean / median imputation for numerical variables, or 
frequent category imputation for categorical variables. We can also use random sample imputation 
together with adding a missing indicator for both categorical and numerical variables.

Commonly used together:

- Mean / median imputation + missing indicator (Numerical variables)
- Frequent category imputation + missing indicator (Categorical variables)
- Random sample Imputation + missing indicator (Numerical and categorical)

### Assumptions

- Data is not missing at random
- Missing data are predictive

### Advantages

- Easy to implement
- Captures the importance of missing data if there is one

### Limitations

- Expands the feature space
- Original variable still needs to be imputed to remove the NaN

Adding a missing indicator will increase 1 variable per variable in the dataset with missing values. 
So if the dataset contains 10 features, and all of them have missing values, after adding a missing 
indicator we will have a dataset with 20 features: the original 10 features plus additional 10 binary 
features, which indicate for each of the original variables whether the value was missing or not. 
This may not be a problem in datasets with tens to a few hundreds variables, but if our original 
dataset contains thousands of variables, by creating an additional variable to indicate NA, we will 
end up with very big datasets. 

#### Important

In addition, data tends to be missing for the same observation across multiple variables, which often leads 
to many of the missing indicator variables to be actually similar or identical to each other.

### Final note

Typically, mean / median / mode imputation is done together with adding a variable to capture those 
observations where the data was missing, thus covering 2 angles: if the data was missing completely at 
random, this would be contemplated by the mean / median / mode imputation, and if it wasn't this would be 
captured by the missing indicator.

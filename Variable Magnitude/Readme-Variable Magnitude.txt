## Variable magnitude

### Does the magnitude of the variable matter?

In Linear Regression models, the scale of variables used to estimate the output matters. Linear models are of the type **y = w x + b**, where the regression coefficient w represents the expected change in y for a one unit change in x (the predictor). Thus, the magnitude of w is partly determined by the magnitude of the units being used for x. If x is a distance variable, just changing the scale from kilometers to miles will cause a change in the magnitude of the coefficient.

In addition, in situations where we estimate the outcome y by contemplating multiple predictors x1, x2, ...xn, predictors with greater numeric ranges dominate over those with smaller numeric ranges.

Gradient descent converges faster when all the predictors (x1 to xn) are within a similar scale, therefore having features in a similar scale is useful for Neural Networks as well as.

In Support Vector Machines, feature scaling can decrease the time to find the support vectors.

Finally, methods using Euclidean distances or distances in general are also affected by the magnitude of the features, as Euclidean distance is sensitive to variations in the magnitude or scales of the predictors. Therefore feature scaling is required for methods that utilise distance calculations like k-nearest neighbours (KNN) and k-means clustering.

In summary:

#### Magnitude matters because:

- The regression coefficient is directly influenced by the scale of the variable
- Variables with bigger magnitude / value range dominate over the ones with smaller magnitude / value range
- Gradient descent converges faster when features are on similar scales
- Feature scaling helps decrease the time to find support vectors for SVMs
- Euclidean distances are sensitive to feature magnitude.

#### The machine learning models affected by the magnitude of the feature are:

- Linear and Logistic Regression
- Neural Networks
- Support Vector Machines
- KNN
- K-means clustering
- Linear Discriminant Analysis (LDA)
- Principal Component Analysis (PCA)

#### Machine learning models insensitive to feature magnitude are the ones based on Trees:

- Classification and Regression Trees
- Random Forests
- Gradient Boosted Trees
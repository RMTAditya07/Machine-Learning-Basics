# Machine-Learning-Basics

`OneHotEncoder` : This class is used for one-hot encoding categorical variables in scikit-learn, which is a popular machine learning library in Python. One-hot encoding is a technique used to convert categorical data into a numerical format that can be used by machine learning algorithms.

```
# Sample categorical data
categories = ['cat', 'dog', 'fish', 'dog', 'cat']

# Create an instance of OneHotEncoder
encoder = OneHotEncoder()

# Fit the encoder to the data and transform the data
encoded_data = encoder.fit_transform(np.array(categories).reshape(-1, 1))

# The result is a sparse matrix containing one-hot encoded vectors
print(encoded_data.toarray())

```
Output : 
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]
 [0. 1. 0.]
 [1. 0. 0.]]

## ColumnTransformer
 `from sklearn.compose import ColumnTransformer` is a useful tool for applying different preprocessing steps to different columns or subsets of columns in your dataset. It's particularly handy when you have a dataset with mixed data types (e.g., numerical and categorical features) and you want to apply different transformations to each type of feature.

`ct = ColumnTransformer(transformers=[('encoder', OneHotEncoder(), [3])], remainder='passthrough')`

* ColumnTransformer is being used to define a series of transformations to be applied to columns in a dataset.
* The transformers argument is a list of tuples, where each tuple contains three elements:
* The first element is a string identifier for the transformation. In your case, it's 'encoder'.
* The second element is the transformer itself. Here, you are using the OneHotEncoder() to encode the categorical data.
* The third element is a list of column indices or names that you want to apply this transformation to. In your case, it's [3], which suggests that you want to apply the one-hot encoding transformation to the column at index 3.
* The remainder argument specifies what to do with the columns that are not explicitly listed in the transformers. In your code, it's set to 'passthrough', which means that any columns not specified in the transformers will be included in the output as-is without any transformation. 

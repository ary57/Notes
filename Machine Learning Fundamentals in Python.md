# Classification

## Machine Learning with Scikit-Learn

### Definitions
- **Machine Learning**: - Computers are given ability to learn to make decisions from data.
- **Unsupervised Learning**: Uncovering hidden patterns from unlabeled data.
    - Example: Grouping customers into distinct categories (Clustering).
- **Supervised Learning**:
    - The predicted values are known.
    - Aim: Predict the target values of unseen data, given the features. 
    - Two types of supervised learning:
        1. **Classification**: Target variable consists of categories.
            - example: identifying spam emails from legit ones. 
        1. **Regression**: Target variable is continuous. 
            - example: house prices.

### Naming conventions
- Feature = predictor variable = independent variable.
- Target variable = dependent variable = response variable.

### Prerequisites to using supervised learning
1. Data must be stored in pandas DataFrame of NumPy array.
1. Data must be in numeric format.
1. There can't be any missing values.

### scikit-learn syntax
```python
from sklearn.module import Model
model = Model()
model.fit(X,y) # X = array of features; y = array of target variable values
predictions = model.predict(X_new)
print(predictions)
```

## The classification challenge
To build a classification model (or classifier) to predict the labels of unseen data:
1. Build a model
1. Model learns from labeled data we pass to it.
1. Pass unlabeled data to the model as input.
1. Model predicts the labels of unseen data.

### k-Nearest Neighbors (KNN)
- idea: to predict the label of any data point by looking at the k nearest neighbors and picking the label of labels with a majority.
- Using scikit-learn to fit a classifier:
```python
from sklearn.neighbors import KNeighborClassifier
X = churn_df[["total_day_charge", "total_eve_charge"]].values
y = chrun_df["churn"].values

knn = KNeighborsClassifier(n_neighbors=15)
knn.fit(X,y)

predictions = knn.predict(X_new)
```

## Measuring model performance
- In classification, accuracy is a commonly used metric.
 $$\text{Accuracy} = \frac{\text{correct predictions}}{\text{total observations}}$$
- To test the accuracy, split the data into train and test sets.
    - use the train set to fit the model.
    - use the test set to get the accuracy.
```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=21, stratify=y)
knn = KNeighborsClassifier(n_neighbors=6)
knn.fit(X_train, y_train)
print(knn.score(X_test, y_test))
```

### Model complexity and over/underfitting
We can re-make and re-run the model with varying number of neighbors to find the optimal number of neighbors. 
```python
train_accuracies = {}
test_accuracies = {}
neighbors = np.arrange(1,26)
for neighbor in neighbors:
    knn = KNeighborsClassifier(n_neighbors=neighbor)
    knn.fit(X_train, y_train)
    train_accuracies[neighbor] = knn.score(X_train, y_train)
    test_accuracies[neighbor] = knn.score(X_test, y_test)

# Plotting the result using matplotlib
plt.figure(figsize=(8,6))
plt.title("KNN: Varying Number of Neighbors")
plt.plot(neighbors, train_accuracies.values(), label="Training Accuracy")
plt.plot(neighbors, test_accuracies.values(), label="Testing Accuracy")
plt.legend()
plt.xlabel("Number of Neighbors")
plt.ylabel("Accuracy")
plt.show()
```
<div style="page-break-after: always"></div>

# Regression

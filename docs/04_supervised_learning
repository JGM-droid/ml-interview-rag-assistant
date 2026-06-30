# Supervised Learning Algorithms

## What is Supervised Learning?

Supervised learning is a type of machine learning in which a model learns from labeled data. Each training example contains both the input features (X) and the correct output (y). During training, the algorithm learns the relationship between the features and the target so it can make predictions on new, unseen data.

Examples include:

- Predicting whether a customer will churn.
- Classifying an email as spam or not spam.
- Predicting house prices.
- Estimating insurance costs.

Supervised learning is one of the most commonly used approaches in machine learning because labeled datasets are available for many business problems.

---

## Classification vs Regression

Supervised learning problems fall into two primary categories.

### Classification

Predicts categories.

Examples:

- Fraud or Not Fraud
- Churn or Stay
- Disease or Healthy
- Spam or Not Spam

Common algorithms include:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- Support Vector Machine
- K-Nearest Neighbors
- Neural Networks

---

### Regression

Predicts continuous numerical values.

Examples:

- House Price
- Sales Forecast
- Temperature
- Delivery Time

Common algorithms include:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

---

# Linear Regression

## Purpose

Predicts continuous numerical values.

Examples:

- Home prices
- Revenue
- Salary
- Sales

### Advantages

- Simple
- Fast
- Easy to interpret

### Limitations

- Assumes linear relationships
- Sensitive to outliers
- Requires feature scaling for best performance

---

# Logistic Regression

## Purpose

Despite its name, Logistic Regression is a **classification algorithm**, not a regression algorithm.

It predicts probabilities between 0 and 1 and then assigns observations to classes using a decision threshold.

Common applications include:

- Customer churn
- Fraud detection
- Medical diagnosis
- Spam filtering

### Advantages

- Fast
- Interpretable
- Works well on linearly separable data
- Produces probabilities

### Limitations

- Assumes approximately linear decision boundaries
- Can struggle with complex nonlinear relationships

---

# Decision Trees

Decision Trees split data into branches by repeatedly selecting the feature that best separates the observations.

Each split attempts to increase the purity of the resulting groups.

Advantages:

- Easy to visualize
- Highly interpretable
- Handles numerical and categorical features
- Does not require feature scaling

Limitations:

- Easily overfits
- High variance
- Small data changes can produce very different trees

---

# Random Forest

Random Forest is an ensemble learning algorithm that combines many Decision Trees.

Each tree is trained using:

- A random sample of observations
- A random subset of features

The final prediction is determined by:

Classification:

Majority vote

Regression:

Average prediction

Advantages:

- High accuracy
- Reduces overfitting
- Robust to noise
- Estimates feature importance

Limitations:

- Less interpretable than a single tree
- Larger models
- Slower than Decision Trees

---

# Gradient Boosting

Gradient Boosting builds trees sequentially.

Each new tree attempts to correct the mistakes made by previous trees.

Popular implementations include:

- XGBoost
- LightGBM
- CatBoost

Advantages:

- Excellent predictive performance
- Frequently wins machine learning competitions
- Handles complex relationships

Limitations:

- Longer training time
- More hyperparameters
- Can overfit if not tuned

---

# Support Vector Machine (SVM)

Support Vector Machines find the decision boundary that maximizes the margin between classes.

Advantages:

- Effective on small datasets
- Works well with high-dimensional data
- Kernel trick captures nonlinear relationships

Limitations:

- Slow on large datasets
- Requires feature scaling
- Difficult to interpret

---

# K-Nearest Neighbors (KNN)

KNN predicts based on the labels of nearby observations.

Advantages:

- Very simple
- No explicit training
- Easy to understand

Limitations:

- Slow during prediction
- Sensitive to feature scaling
- Sensitive to irrelevant features

---

# Naive Bayes

Naive Bayes uses probability theory and assumes features are conditionally independent.

Common applications include:

- Spam detection
- Text classification
- Sentiment analysis

Advantages:

- Extremely fast
- Works well on text data
- Performs well with small datasets

Limitations:

- Independence assumption is often unrealistic

---

# Ensemble Learning

Ensemble methods combine multiple models to improve performance.

Common ensemble algorithms include:

- Random Forest
- Gradient Boosting
- XGBoost
- AdaBoost

Ensemble models generally achieve higher accuracy than individual models but sacrifice interpretability.

---

# Algorithm Comparison

| Algorithm | Classification | Regression | Scaling Needed | Interpretable | Handles Nonlinear Data |
|------------|---------------|------------|----------------|----------------|------------------------|
| Linear Regression | ❌ | ✅ | Usually | ✅ | ❌ |
| Logistic Regression | ✅ | ❌ | Usually | ✅ | Limited |
| Decision Tree | ✅ | ✅ | No | High | Yes |
| Random Forest | ✅ | ✅ | No | Medium | Yes |
| Gradient Boosting | ✅ | ✅ | No | Medium | Yes |
| SVM | ✅ | Limited | Yes | Low | Yes |
| KNN | ✅ | ✅ | Yes | Medium | Limited |
| Naive Bayes | ✅ | ❌ | No | Medium | Limited |

---

# Choosing the Right Algorithm

General guidelines:

Use Logistic Regression when:

- Baseline model
- High interpretability
- Binary classification

Use Decision Trees when:

- Explainability is important
- Fast prototyping

Use Random Forest when:

- Strong baseline performance
- Minimal preprocessing
- Reduced overfitting

Use Gradient Boosting when:

- Maximizing predictive accuracy
- Kaggle competitions
- Structured tabular data

Use SVM when:

- Small datasets
- High-dimensional features

Use KNN when:

- Simple problems
- Small datasets

Use Naive Bayes when:

- NLP tasks
- Text classification
- Spam detection

---

# Common scikit-learn Classes

Frequently used models include:

- LinearRegression
- LogisticRegression
- DecisionTreeClassifier
- DecisionTreeRegressor
- RandomForestClassifier
- RandomForestRegressor
- GradientBoostingClassifier
- GradientBoostingRegressor
- KNeighborsClassifier
- KNeighborsRegressor
- SVC
- SVR
- GaussianNB

---

# Interview Tips

Interviewers often ask:

- Why did you choose Random Forest instead of Logistic Regression?
- Why wasn't Decision Tree your final model?
- Why did you compare multiple algorithms?
- Which algorithms require feature scaling?
- Which algorithm is easiest to explain to business stakeholders?

Strong answers compare multiple models before selecting the final one based on validation performance and business requirements rather than personal preference.

---

# Key Takeaways

- Supervised learning learns from labeled data.
- Classification predicts categories, while regression predicts continuous values.
- Logistic Regression is a classification algorithm despite its name.
- Decision Trees are interpretable but prone to overfitting.
- Random Forest reduces overfitting by averaging many trees.
- Gradient Boosting builds trees sequentially to improve errors.
- Choosing the best algorithm depends on the dataset, business problem, interpretability requirements, and evaluation metrics.
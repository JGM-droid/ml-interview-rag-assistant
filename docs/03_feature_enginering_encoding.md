# Feature Engineering & Encoding

## What is Feature Engineering?

Feature engineering is the process of creating, transforming, selecting, or modifying input variables so a machine learning model can learn useful patterns more effectively. While data preprocessing focuses on cleaning raw data, feature engineering focuses on improving the information available to the model.

Good features can improve model performance more than switching to a more complex algorithm. For example, a model predicting customer churn may perform better if we create features such as account age, average monthly usage, number of support tickets, payment history, or recent activity changes.

Feature engineering is important because machine learning models do not understand raw business context automatically. The data scientist must help convert raw data into meaningful signals.

---

## Common Types of Feature Engineering

Common feature engineering techniques include:

- Creating new numerical features
- Combining existing columns
- Extracting date and time features
- Encoding categorical variables
- Scaling numerical variables
- Handling skewed distributions
- Selecting useful features
- Removing redundant or noisy features

For example, from a `signup_date` column, we can create features such as `account_age_days`, `signup_month`, `signup_year`, or `is_weekend_signup`. From transaction data, we can create `total_spend`, `average_order_value`, or `days_since_last_purchase`.

---

## Encoding Categorical Variables

Machine learning models usually require numerical input, so categorical variables must often be converted into numbers.

A categorical variable is a feature that contains categories instead of continuous numeric values. Examples include:

- `gender`
- `city`
- `plan_type`
- `education_level`
- `product_category`
- `payment_method`

Encoding transforms these categories into a format that machine learning algorithms can use.

---

## One-Hot Encoding

One-hot encoding creates a separate binary column for each category.

Example:

Original feature:

| color |
|---|
| red |
| blue |
| green |

After one-hot encoding:

| color_red | color_blue | color_green |
|---|---|---|
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 0 | 0 | 1 |

One-hot encoding is useful when categories do not have a natural order. For example, city names, product types, and payment methods usually should not be treated as ranked values.

Interview tip: One-hot encoding prevents the model from assuming that one category is greater than another. For example, encoding `red = 1`, `blue = 2`, and `green = 3` would incorrectly suggest that green is greater than blue.

Limitations of one-hot encoding:

- It can create many new columns if a feature has many unique categories.
- It can increase memory usage.
- It may make the feature space sparse.

---

## Label Encoding

Label encoding assigns each category an integer value.

Example:

| size | encoded_size |
|---|---|
| small | 0 |
| medium | 1 |
| large | 2 |

Label encoding can be useful when the categories have a meaningful order, such as:

- low, medium, high
- small, medium, large
- beginner, intermediate, advanced

However, label encoding can be dangerous for unordered categories. If we encode cities as `Austin = 0`, `Dallas = 1`, and `Houston = 2`, some models may interpret Houston as greater than Dallas, even though there is no real ranking.

Interview tip: Use label encoding carefully. It is appropriate for ordinal variables but can introduce false order into nominal variables.

---

## Ordinal Encoding

Ordinal encoding is similar to label encoding, but it is specifically used when categories have a real order.

Example:

| education_level | encoded |
|---|---|
| high_school | 0 |
| bachelors | 1 |
| masters | 2 |
| phd | 3 |

Ordinal encoding is appropriate because the categories have a meaningful progression.

---

## Scaling and Normalization

Scaling changes numerical features so they are on comparable ranges.

This matters for algorithms that rely on distance, gradients, or feature magnitude, such as:

- Logistic Regression
- Linear Regression
- K-Nearest Neighbors
- Support Vector Machines
- Neural Networks
- Principal Component Analysis

Tree-based models such as Decision Trees, Random Forests, and Gradient Boosting usually do not require feature scaling because they split data based on thresholds.

Common scaling methods:

- Standardization: centers data around mean 0 and standard deviation 1
- Min-max scaling: rescales values between 0 and 1
- Robust scaling: uses median and interquartile range, useful when outliers exist

Interview tip: Scaling should be fitted only on the training data, then applied to validation and test data. Fitting the scaler on the full dataset can cause data leakage.

---

## Feature Selection

Feature selection means choosing the most useful input variables and removing irrelevant, redundant, or noisy features.

Reasons to perform feature selection:

- Improve model performance
- Reduce overfitting
- Improve training speed
- Make the model easier to interpret
- Remove features that add noise

Common feature selection approaches include:

- Removing columns with too many missing values
- Removing duplicate or highly correlated features
- Using domain knowledge
- Checking feature importance from tree-based models
- Using regularization such as L1/Lasso

Feature selection is especially useful when the dataset has many columns or when some features are not related to the target variable.

---

## Data Leakage in Feature Engineering

Data leakage happens when information from outside the training process is accidentally used to build the model.

Examples of leakage:

- Scaling using the full dataset before train/test split
- Encoding categories using information from the test set
- Creating features using future information
- Including columns that directly reveal the target

For example, if we predict loan default and include a column called `default_date`, the model may perform extremely well during testing but fail in the real world because that information would not be available at prediction time.

Interview tip: Always ask whether the feature would be available at the time the prediction is made.

---

## Feature Engineering Examples

For a customer churn model, useful engineered features might include:

- Account age
- Number of support tickets
- Recent login frequency
- Average monthly spend
- Change in usage over the last 30 days
- Whether the customer downgraded their plan
- Days since last activity

For a movie review sentiment model, useful features might include:

- TF-IDF scores
- Word counts
- N-grams
- Presence of positive or negative words
- Embeddings from a language model

For a computer vision model, feature engineering is often handled automatically by convolutional neural networks, which learn edges, textures, shapes, and higher-level visual patterns from images.

---

## Interview Questions and Strong Answers

### What is feature engineering?

Feature engineering is the process of transforming raw data into useful input features that help a model learn patterns. It can include creating new columns, encoding categorical variables, scaling numerical values, extracting date features, or selecting the most relevant variables.

### What is the difference between preprocessing and feature engineering?

Preprocessing cleans the data so it is usable. Feature engineering improves the data so it is more predictive. For example, filling missing values is preprocessing, while creating `account_age_days` from a signup date is feature engineering.

### What is the difference between one-hot encoding and label encoding?

One-hot encoding creates separate binary columns for each category and is best for unordered categories. Label encoding assigns integer values to categories and is best when the categories have a meaningful order. Using label encoding on unordered categories can accidentally create a false ranking.

### When do you need scaling?

Scaling is important for models that depend on distances, gradients, or feature magnitude, such as Logistic Regression, KNN, SVMs, and Neural Networks. Tree-based models such as Decision Trees and Random Forests usually do not require scaling.

### How can feature engineering cause data leakage?

Feature engineering can cause leakage if it uses information that would not be available when making real predictions. Examples include using future data, fitting transformations on the full dataset before splitting, or including columns that directly reveal the target.

---

## Key Takeaways

- Feature engineering improves the information available to a machine learning model.
- Encoding converts categorical variables into numerical form.
- One-hot encoding is best for unordered categories.
- Label or ordinal encoding is best for ordered categories.
- Scaling matters for linear, distance-based, gradient-based, and neural network models.
- Tree-based models usually do not require scaling.
- Feature selection can reduce noise and improve interpretability.
- Data leakage must be avoided by fitting transformations only on training data.
- Strong features can improve model performance more than simply choosing a more complex algorithm.
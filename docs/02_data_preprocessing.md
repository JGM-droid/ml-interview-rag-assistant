# Data Preprocessing

## What is Data Preprocessing?

Data preprocessing is the process of cleaning, organizing, and transforming raw data into a format that can be used to train machine learning models. Real-world datasets are rarely perfect—they often contain missing values, duplicate records, inconsistent formatting, outliers, and categorical variables that must be converted into numerical values.

Many data scientists estimate that data cleaning and preprocessing account for **60–80% of a machine learning project's development time**. Even the most advanced algorithms perform poorly when trained on low-quality data, making preprocessing one of the most important stages of the machine learning workflow.

---

## Step 1: Understand the Dataset

Before modifying the data, it is important to understand what the dataset contains.

Common questions include:

* How many rows and columns are present?
* What data types does each feature have?
* Are there missing values?
* Are there duplicate records?
* Which features are numerical or categorical?
* Is the target variable balanced?
* Are there obvious outliers?

### Common Pandas Commands

| Function            | Purpose                                                |
| ------------------- | ------------------------------------------------------ |
| `df.head()`         | Display the first few rows of the dataset.             |
| `df.tail()`         | Display the last few rows.                             |
| `df.shape`          | Show the number of rows and columns.                   |
| `df.columns`        | Display all column names.                              |
| `df.info()`         | Display data types, non-null counts, and memory usage. |
| `df.describe()`     | Generate summary statistics for numerical columns.     |
| `df.dtypes`         | Display each column's data type.                       |
| `df.value_counts()` | Count unique values in a column.                       |

**Interview Tip:** Always inspect your data before cleaning it. Understanding the dataset helps determine which preprocessing techniques are appropriate.

---

## Step 2: Handle Missing Values

Missing values occur when information is unavailable for one or more observations.

Examples include:

* Missing age
* Unknown income
* Blank customer location

Ignoring missing values can reduce model performance or cause some algorithms to fail.

### Common Strategies

* Fill numerical values with the **mean**
* Fill numerical values with the **median**
* Fill categorical values with the **mode**
* Replace with a constant such as 0 or "Unknown"
* Remove rows or columns when appropriate

### Mean vs. Median

**Mean**

* Uses the average.
* Sensitive to outliers.

**Median**

* Uses the middle value.
* More robust when extreme values exist.

Example:

Ages:

```
22, 24, 25, 27, 120
```

Mean = 43.6

Median = 25

Since the value 120 is an outlier, the median is usually the better choice.

### Common Pandas Commands

| Function          | Purpose                                           |
| ----------------- | ------------------------------------------------- |
| `df.isna()`       | Identify missing values.                          |
| `df.isna().sum()` | Count missing values in each column.              |
| `df.fillna()`     | Replace missing values.                           |
| `df.dropna()`     | Remove rows or columns containing missing values. |

**Interview Tip:** Explain *why* you selected a particular filling strategy. Simply saying "I used `fillna()`" is not enough.

---

## Step 3: Remove Duplicate Records

Duplicate observations occur when identical rows appear multiple times.

Duplicates can:

* Bias model training
* Distort summary statistics
* Artificially increase dataset size

### Common Pandas Commands

| Function                | Purpose                   |
| ----------------------- | ------------------------- |
| `df.duplicated()`       | Identify duplicate rows.  |
| `df.duplicated().sum()` | Count duplicate rows.     |
| `df.drop_duplicates()`  | Remove duplicate records. |

---

## Step 4: Detect Outliers

Outliers are observations that differ significantly from the rest of the dataset.

Outliers may represent:

* Data entry mistakes
* Measurement errors
* Legitimate but rare events

Before removing outliers, determine whether they contain valuable information.

Common visualization techniques include:

* Box plots
* Histograms
* Scatter plots

---

## Step 5: Feature Scaling

Some machine learning algorithms perform better when numerical features share a similar scale.

Algorithms that usually benefit from scaling include:

* Logistic Regression
* K-Nearest Neighbors
* Support Vector Machines
* Neural Networks

Tree-based algorithms generally **do not require scaling**, including:

* Decision Trees
* Random Forests
* Gradient Boosting

Common scaling methods:

**Standardization**

* Mean becomes 0
* Standard deviation becomes 1

**Min-Max Scaling**

* Rescales values between 0 and 1

---

## Step 6: Encode Categorical Variables

Most machine learning models cannot train directly on text.

Examples:

* Red
* Blue
* Green

must be converted into numerical values.

### Label Encoding

Assigns each category an integer.

Example:

```
Small  → 0
Medium → 1
Large  → 2
```

Best suited for ordinal categories where order matters.

### One-Hot Encoding

Creates a separate binary column for each category.

Example:

| Color_Red | Color_Blue | Color_Green |
| --------- | ---------- | ----------- |
| 1         | 0          | 0           |
| 0         | 1          | 0           |
| 0         | 0          | 1           |

Best suited for nominal categories where no natural ordering exists.

**Interview Tip:** One-Hot Encoding avoids introducing artificial numerical relationships between categories.

---

## Step 7: Handle Class Imbalance

Class imbalance occurs when one target class appears much more frequently than another.

Example:

* 95% customers stay
* 5% customers leave

A model predicting every customer stays would achieve 95% accuracy while providing little practical value.

Common techniques include:

* Upsampling the minority class
* Downsampling the majority class
* Applying class weights
* Adjusting the classification threshold

Better evaluation metrics include:

* Precision
* Recall
* F1 Score
* ROC-AUC

---

## Common Pandas Functions Used During Preprocessing

| Function               | Purpose                                                       |
| ---------------------- | ------------------------------------------------------------- |
| `df.info()`            | Inspect the dataset.                                          |
| `df.describe()`        | Generate summary statistics.                                  |
| `df.isna().sum()`      | Count missing values.                                         |
| `df.fillna()`          | Replace missing values.                                       |
| `df.dropna()`          | Remove missing values.                                        |
| `df.duplicated()`      | Detect duplicate rows.                                        |
| `df.drop_duplicates()` | Remove duplicate rows.                                        |
| `df.groupby()`         | Group observations for analysis.                              |
| `df.agg()`             | Apply aggregation functions such as mean, sum, max, or count. |
| `df.merge()`           | Combine multiple DataFrames using a common key.               |
| `df.sort_values()`     | Sort rows by one or more columns.                             |
| `df.value_counts()`    | Count occurrences of unique values.                           |
| `df.loc[]`             | Select rows and columns by label.                             |
| `df.iloc[]`            | Select rows and columns by integer position.                  |
| `df.query()`           | Filter rows using logical expressions.                        |
| `df.assign()`          | Create new columns without modifying the original DataFrame.  |
| `df.apply()`           | Apply a function across rows or columns.                      |

---

## Interview Tips

* Always explain **why** you performed each preprocessing step.
* Inspect data before making changes.
* Use the median instead of the mean when significant outliers exist.
* Do not automatically remove outliers without understanding their cause.
* Scale features only when the chosen algorithm benefits from scaling.
* Tree-based models generally do not require feature scaling.
* Choose One-Hot Encoding for nominal variables and Label Encoding for ordinal variables.
* When classes are imbalanced, rely on Precision, Recall, F1 Score, or ROC-AUC instead of accuracy alone.

---

## Key Takeaways

* Data preprocessing prepares raw data for machine learning.
* High-quality data is often more valuable than a more complex algorithm.
* Understanding the dataset should always come before cleaning it.
* Missing values, duplicates, outliers, scaling, encoding, and class imbalance are fundamental preprocessing concepts.
* Strong interview answers explain the reasoning behind preprocessing decisions rather than simply naming functions.

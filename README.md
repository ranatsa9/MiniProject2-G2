# MiniProject2-G2

# Titanic Survival Prediction Using Naive Bayes

## Project Overview

This project applies the **Gaussian Naive Bayes classification algorithm** to the Titanic dataset to predict whether a passenger survived.

The project includes:

* Dataset exploration
* Data cleaning
* Exploratory Data Analysis
* Feature preprocessing
* Model training
* Model evaluation
* Hyperparameter tuning
* Comparison with Logistic Regression

## Project Objective

The objective is to predict passenger survival based on features such as:

* Passenger class
* Gender
* Age
* Number of family members
* Ticket fare
* Embarkation port

The target variable is:

* `0` — Did not survive
* `1` — Survived

## Dataset

The project uses the Titanic training dataset.

Dataset summary:

* **891 passengers**
* **12 original columns**
* **342 passengers survived**
* **38.4% survival rate**

Main columns used in the project:

| Feature    | Description                          |
| ---------- | ------------------------------------ |
| `Pclass`   | Passenger class                      |
| `Sex`      | Passenger gender                     |
| `Age`      | Passenger age                        |
| `SibSp`    | Number of siblings or spouses aboard |
| `Parch`    | Number of parents or children aboard |
| `Fare`     | Ticket fare                          |
| `Embarked` | Passenger embarkation port           |
| `Survived` | Target variable                      |

## Exploratory Data Analysis

The EDA included:

* Exploring the dataset structure
* Reviewing data types
* Checking missing values
* Examining survival distribution
* Comparing survival by gender
* Comparing survival by passenger class
* Examining age and fare distributions
* Visualizing correlations between numerical variables

The analysis showed that gender and passenger class had strong relationships with survival.

## Data Preprocessing

The following preprocessing steps were applied:

1. Missing age values were filled using the median.
2. Missing embarkation values were filled using the mode.
3. The `Cabin` column was excluded because it contained a high percentage of missing values.
4. Unnecessary identifiers such as `PassengerId`, `Name`, and `Ticket` were excluded from the model features.
5. Categorical variables were converted into numerical values using one-hot encoding.
6. The dataset was divided into:

   * **80% training data**
   * **20% testing data**
7. Stratified splitting was used to maintain the survival-class proportions.

After preprocessing, the model used **9 input features**.

## Model

The main model used in this project is:

### Gaussian Naive Bayes

Gaussian Naive Bayes uses Bayes’ theorem to calculate the probability that a passenger belongs to each survival class.

It assumes that the input features are independent and that continuous numerical features approximately follow a normal distribution.

This model was selected because the Titanic dataset contains both encoded categorical features and continuous numerical features such as age and fare.

## Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Classification report
* Confusion matrix

### Gaussian Naive Bayes Results

| Metric    | Result |
| --------- | -----: |
| Accuracy  |  78.2% |
| Precision |  71.4% |
| Recall    |  72.5% |
| F1 Score  |  71.9% |

## Confusion Matrix

| Actual result       | Predicted Non-Survivor | Predicted Survivor |
| ------------------- | ---------------------: | -----------------: |
| Actual Non-Survivor |                     90 |                 20 |
| Actual Survivor     |                     19 |                 50 |

The model correctly predicted:

* 90 passengers who did not survive
* 50 passengers who survived

It incorrectly predicted:

* 20 non-survivors as survivors
* 19 survivors as non-survivors

## Hyperparameter Tuning

Hyperparameter tuning was performed as an optional improvement step.

The best cross-validation accuracy was approximately:

**79.9%**

The tuned Gaussian Naive Bayes model achieved a test accuracy of:

**78.2%**

The tuning process did not significantly improve the final test accuracy.

## Model Comparison

Gaussian Naive Bayes was compared with Logistic Regression.

| Model                | Accuracy | F1 Score |
| -------------------- | -------: | -------: |
| Gaussian Naive Bayes |    78.2% |    71.9% |
| Logistic Regression  |    80.4% |    72.9% |

Logistic Regression performed slightly better, but Gaussian Naive Bayes still provided a reasonable and interpretable baseline model.

## Key Findings

* Female passengers had a higher survival rate than male passengers.
* First-class passengers had a higher survival rate than second- and third-class passengers.
* Passenger class, gender, age, and fare were useful predictors.
* Gaussian Naive Bayes correctly classified most passengers.
* The model performed reasonably well despite its assumption that features are independent.
* Logistic Regression achieved slightly better results.

## Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Repository Structure

```text
Titanic-Naive-Bayes/
│
├── MiniProject_G2_U3.ipynb
├── train.csv
├── Titanic_Naive_Bayes_Presentation.pptx
└── README.md
```

## How to Run the Project

1. Clone the repository:

```bash
git clone YOUR_REPOSITORY_LINK
```

2. Open the project folder.

3. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

4. Start Jupyter Notebook:

```bash
jupyter notebook
```

5. Open the notebook and run all cells in order.

Make sure that `train.csv` is located in the same folder as the notebook.

## Conclusion

The Gaussian Naive Bayes model achieved an accuracy of **78.2%** when predicting Titanic passenger survival.

The results demonstrate how a classification algorithm can be used to identify patterns in real-world data. Although Logistic Regression performed slightly better, Gaussian Naive Bayes produced a good baseline result and was simple to train and interpret.

Possible future improvements include creating new features such as family size, extracting passenger titles from names, testing additional classification algorithms, and applying more advanced feature engineering.

## Team Members

* Team Member 1
* Team Member 2
* Team Member 3
* Team Member 4

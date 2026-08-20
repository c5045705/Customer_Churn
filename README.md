# Customer_Churn

# Author Name : Harshitha Kotla
# Student id : c5045705
## Project Overview

This dissertation project develops and evaluates a machine learning and
deep learning framework for predicting bank customer churn. The project
investigates whether customers are likely to leave a banking service
based on demographic, financial, account and behavioural
characteristics.

The project evaluates Logistic Regression, Random Forest, XGBoost and
Artificial Neural Network models under a consistent experimental
workflow. The workflow includes data preprocessing, feature engineering,
class balancing using SMOTE, baseline model development, hyperparameter
optimisation using Grid Search and Randomized Search, Five-Fold
Cross-Validation, performance evaluation and SHAP-based feature
analysis.

The final model selected for the dissertation is the Grid Search
optimised XGBoost model because it provided the strongest overall
predictive performance, strong cross-validation performance and a
favourable balance between predictive capability and resource
requirements.

## Dissertation Aim

The main aim of the dissertation is to evaluate machine learning and
deep learning models for bank customer churn prediction using
Hyperparameter Optimisation, Five-Fold Cross-Validation and SHAP
analysis while considering predictive performance and resource usage.

## Research Question

How effectively can Machine Learning and Deep Learning models predict
bank customer churn through Hyperparameter Optimisation and Five-Fold
Cross-Validation while balancing predictive performance and resource
usage?

## Objectives

### Objective 1

Evaluate suitable machine learning and deep learning techniques for
identifying customers at risk of bank churn.

### Objective 2

Prepare and balance the churn dataset through data preprocessing,
feature engineering and Synthetic Minority Oversampling Technique.

### Objective 3

Optimise selected models using GridSearchCV and RandomizedSearchCV to
identify effective hyperparameter configurations.

### Objective 4

Assess and validate model performance using Accuracy, Weighted F1-Score,
ROC-AUC, training time, prediction time, memory usage and Five-Fold
Cross-Validation.

### Objective 5

Apply SHAP analysis and risk-based decision support to identify
influential churn factors and translate model outputs into
customer-retention insights.

## Dataset

The project uses a publicly available banking customer churn dataset.

### Dataset characteristics

-   Number of records: 10,000
-   Number of features: 14
-   Prediction type: Binary classification
-   Target variable: Exited
-   Target value 0: Customer retained
-   Target value 1: Customer churned
-   Data source: Kaggle Bank Customer Churn Prediction Dataset

The dataset contains demographic, financial and account-related
information suitable for modelling customer churn.

## Data Preprocessing

The following preprocessing workflow was implemented:

1.  Dataset loading and initial inspection.
2.  Identification of the target variable.
3.  Checking the dataset structure and data quality.
4.  Removal of duplicate records.
5.  Handling of missing values.
6.  Encoding of categorical variables.
7.  Standardisation of numerical features.
8.  Feature engineering.
9.  Stratified train-test splitting.
10. Class balancing using SMOTE on the training data only.
11. Model training using the prepared feature set.

The dataset was divided into 80 percent training data and 20 percent
testing data.

SMOTE was applied only to the training dataset to avoid introducing
synthetic observations into the independent test set. This produced a
balanced training dataset and reduced the effect of the original class
imbalance.

## Machine Learning Models

### Logistic Regression

Logistic Regression was included as a traditional linear baseline model.
It provides a computationally efficient benchmark against which more
complex algorithms can be compared.

### Random Forest

Random Forest is an ensemble learning method based on multiple decision
trees. It was selected because it can model non-linear relationships and
reduce prediction variance through ensemble learning.

### XGBoost

XGBoost is a gradient boosting algorithm that sequentially improves weak
learners by correcting previous prediction errors. It was selected
because of its strong performance on structured datasets and its ability
to model complex feature interactions.

### Artificial Neural Network

An Artificial Neural Network was included to provide a deep learning
comparison. The ANN consists of interconnected input, hidden and output
layers and can learn non-linear relationships between customer
characteristics and churn outcomes.

## Hyperparameter Optimisation

Two optimisation approaches were used:

### Grid Search

Grid Search evaluates predefined combinations of hyperparameter values
systematically. It was used to identify strong parameter configurations
for the selected machine learning models.

### Randomized Search

Randomized Search evaluates a selected number of randomly sampled
parameter combinations from the defined search space. It provides an
alternative optimisation strategy when the search space contains many
possible combinations.

The optimisation process was combined with cross-validation to identify
effective model configurations.

## Five-Fold Cross-Validation

Five-Fold Cross-Validation was used to evaluate model stability and
generalisation.

The available training data was divided into five folds. Four folds were
used for training and one fold was used for validation in each
iteration. The process was repeated until each fold had been used as the
validation fold.

This provided a more reliable assessment than relying on a single
train-test split.

## Evaluation Metrics

The models were evaluated using multiple measures rather than accuracy
alone.

### Accuracy

Accuracy measures the proportion of correctly classified observations.

### Weighted F1-Score

Weighted F1-Score combines precision and recall while taking the class
distribution into account.

### ROC-AUC

ROC-AUC measures the ability of the classifier to distinguish between
churned and retained customers across different classification
thresholds.

### Training Time

Training time measures how long the model requires to learn from the
training data.

### Prediction Time

Prediction time measures the time required to generate predictions for
the test data.

### Memory Usage

Memory usage measures the memory required by the model during the
evaluation process.

## Baseline Results

The baseline evaluation established the performance of the models before
hyperparameter optimisation.

  ------------------------------------------------------------------------
  Model                                     Accuracy Key Finding
  --------------------- ---------------------------- ---------------------
  Logistic Regression        Lower than the ensemble Fastest baseline and
                                              models useful benchmark

  Random Forest                               84.20% Strong ensemble
                                                     performance

  XGBoost                                     84.70% Highest baseline
                                                     accuracy

  ANN                                         79.50% Strong ROC-AUC but
                                                     higher resource
                                                     requirements
  ------------------------------------------------------------------------

The baseline results showed that XGBoost achieved the highest accuracy
at 84.70 percent and a Weighted F1-Score of 84.13 percent. Random Forest
achieved 84.20 percent accuracy and a Weighted F1-Score of 84.19
percent. ANN achieved 79.50 percent accuracy but produced the highest
baseline ROC-AUC of 0.8538.

Logistic Regression was the most computationally efficient baseline
model, with a reported training time of approximately 0.0196 seconds and
prediction time of approximately 0.0079 seconds.

These results established the benchmark for the subsequent optimisation
and validation stages.

## Hyperparameter Optimisation Results

Hyperparameter optimisation improved the performance of the stronger
ensemble models.

The most important result was obtained from the Grid Search optimised
XGBoost model.

### Optimised XGBoost

-   Test accuracy: 86.25 percent
-   ROC-AUC: 85.80 percent as reported in the presentation results
-   Five-Fold Cross-Validation accuracy: 90.29 percent
-   Final model selection: Yes

The optimised XGBoost model achieved the highest overall classification
accuracy and was selected as the final predictive model.

Random Forest also remained a strong model after optimisation, with a
reported optimised accuracy of 84.45 percent using Grid Search.

The optimisation results indicate that tuning model parameters can
improve predictive performance compared with default model
configurations, particularly for ensemble learning algorithms.

## Five-Fold Cross-Validation Results

The Five-Fold Cross-Validation results provided additional evidence
regarding model stability.

  Model                   Mean Five-Fold Validation Accuracy
  --------------------- ------------------------------------
  Logistic Regression                                 71.30%
  Random Forest                                       89.48%
  XGBoost                                             90.29%
  ANN                                                 79.33%

XGBoost achieved the highest mean Five-Fold Cross-Validation accuracy of
90.29 percent.

Random Forest achieved 89.48 percent.

The reported standard deviations across the evaluated models were low,
approximately between 0.0062 and 0.0083, indicating limited variation
between validation folds.

The cross-validation results therefore supported the selection of
XGBoost as the strongest overall model in the dissertation.

## SHAP Analysis

SHAP analysis was applied to the selected XGBoost model to identify
influential features contributing to churn predictions.

The analysis identified the following important churn-related factors:

-   Age
-   Number of Products
-   Tenure
-   Active Membership

Age was reported as the most influential feature, with a mean SHAP value
of approximately 1.0350.

The SHAP analysis therefore provided feature-level information that
could support banking customer-retention analysis.

## Final Model

The final predictive model selected for the dissertation is the Grid
Search optimised XGBoost model.

The selection was based on several factors:

1.  Highest overall test accuracy.
2.  Strong Weighted F1-Score.
3.  Strong ROC-AUC performance.
4.  Highest mean Five-Fold Cross-Validation accuracy.
5.  Low variation across validation folds.
6.  Strong performance compared with Logistic Regression, Random Forest
    and ANN.
7.  More favourable resource requirements than the ANN.
8.  Strong suitability for structured banking customer data.

The final model achieved 86.25 percent test accuracy and 90.29 percent
mean Five-Fold Cross-Validation accuracy.

## System Workflow

The overall project workflow is:

### Step 1: Dataset Collection

Obtain the publicly available bank customer churn dataset.

### Step 2: Data Inspection

Inspect records, variables, data types, missing values, duplicates and
the target distribution.

### Step 3: Data Preprocessing

Clean the data, encode categorical variables and standardise numerical
features.

### Step 4: Feature Engineering

Prepare the customer attributes for predictive modelling.

### Step 5: Train-Test Split

Divide the dataset into 80 percent training data and 20 percent testing
data.

### Step 6: SMOTE

Apply SMOTE only to the training dataset to balance the churn and
non-churn classes.

### Step 7: Baseline Modelling

Train Logistic Regression, Random Forest, XGBoost and ANN using their
baseline configurations.

### Step 8: Baseline Evaluation

Evaluate the models using accuracy, F1-score, ROC-AUC and
resource-related measures.

### Step 9: Hyperparameter Optimisation

Apply Grid Search and Randomized Search to identify improved model
configurations.

### Step 10: Five-Fold Cross-Validation

Evaluate model stability across five validation folds.

### Step 11: SHAP Analysis

Analyse the selected XGBoost model to identify influential customer
features.

### Step 12: Final Model Selection

Select the best-performing model based on comprehensive evaluation.

### Step 13: Decision Support

Use the final model and feature analysis to support customer-retention
decisions.

## Technology and Tools

The project uses Python-based machine learning and data analysis tools.

### Main tools and libraries

-   Python
-   pandas
-   NumPy
-   scikit-learn
-   XGBoost
-   TensorFlow
-   Keras
-   imbalanced-learn
-   SHAP
-   Matplotlib
-   Seaborn
-   GridSearchCV
-   RandomizedSearchCV


## Running the Project

The recommended execution order is:

``` text
1. Load dataset
2. Perform data preprocessing
3. Apply feature engineering
4. Split training and testing data
5. Apply SMOTE to training data
6. Train baseline models
7. Evaluate baseline models
8. Run Grid Search
9. Run Randomized Search
10. Perform Five-Fold Cross-Validation
11. Compare optimised models
12. Select final XGBoost model
13. Perform SHAP analysis
14. Generate final results and visualisations
```

## Important Data Handling Procedure

SMOTE should be applied only to the training data.

The independent test dataset should remain untouched so that final
performance is evaluated on data that was not artificially generated.

The same preprocessing logic used during model development should be
applied consistently when the final model is used for new customer
predictions.

## Key Findings

The main findings of the dissertation are:

### Finding 1: Ensemble models performed strongly

Random Forest and XGBoost produced stronger predictive performance than
Logistic Regression in the baseline evaluation.

### Finding 2: XGBoost was the strongest overall model

XGBoost achieved the highest baseline accuracy and remained the
strongest model after optimisation and cross-validation.

### Finding 3: Hyperparameter optimisation improved model performance

Grid Search and Randomized Search helped identify better parameter
configurations than default model settings.

### Finding 4: Five-Fold Cross-Validation supported model stability

XGBoost achieved the highest mean validation accuracy of 90.29 percent,
while Random Forest achieved 89.48 percent.

### Finding 5: ANN provided strong discrimination but required more resources

ANN achieved a strong ROC-AUC score but required considerably more
training time and memory than the traditional machine learning models.

### Finding 6: SHAP identified important churn factors

Age, Number of Products, Tenure and Active Membership were identified as
influential factors, with Age reported as the most influential feature.

## Final Results Summary

  -----------------------------------------------------------------------
  Evaluation Stage        Best Model              Result
  ----------------------- ----------------------- -----------------------
  Baseline accuracy       XGBoost                 84.70%

  Baseline Weighted F1    XGBoost                 84.13%

  Baseline highest        ANN                     0.8538
  ROC-AUC                                         

  Optimised test accuracy XGBoost                 86.25%

  Mean Five-Fold CV       XGBoost                 90.29%
  accuracy                                        

  Strong alternative      Random Forest           89.48% mean CV accuracy
  ensemble                                        

  Most influential SHAP   Age                     Mean SHAP value
  feature                                         approximately 1.0350

  Final selected model    Grid Search optimised   Selected
                          XGBoost                 
  -----------------------------------------------------------------------

## Limitations

The dissertation identifies several limitations.

### Single Dataset

The evaluation is based on one static banking churn dataset. Therefore,
the findings may not represent every banking environment.

### Static Observations

A static dataset cannot fully capture changes in customer behaviour over
time or temporal churn patterns.

### Dataset Imbalance

Although SMOTE was used to address the training class imbalance,
synthetic oversampling may not perfectly represent real-world
minority-class observations.

### Model Scope

The project evaluates Logistic Regression, Random Forest, XGBoost and
ANN. More advanced deep learning architectures were outside the scope of
the current implementation.

### Generalisation

Further testing using additional banking datasets and longitudinal
customer data would strengthen confidence in the general applicability
of the findings.

## Future Work

Future development could include:

1.  Evaluation using multiple banking datasets.
2.  Use of longitudinal customer data.
3.  Evaluation using real-time behavioural information.
4.  Testing more advanced deep learning architectures.
5.  Investigation of additional class-balancing approaches.
6.  Automated hyperparameter optimisation.
7.  Development of a more advanced banking decision-support interface.
8.  Further investigation of the stability of SHAP feature contributions
    across different datasets.
9.  Integration with real-time customer-retention workflows.
10. Continuous monitoring of model performance after deployment.

## Ethical and Data Protection Considerations

The project uses a publicly available secondary dataset.

The dissertation documentation states that ethical approval was obtained
before conducting the dissertation and that the public secondary dataset
was handled with attention to confidentiality, privacy and GDPR
requirements.

No personally identifiable customer information should be introduced
into the project repository.

Raw datasets containing sensitive or restricted information should not
be uploaded to a public GitHub repository.

## Reproducibility

To reproduce the experiments:

1.  Install the required Python packages.
2.  Obtain the dataset from its permitted public source.
3.  Place the dataset in the appropriate data directory.
4.  Run the preprocessing workflow.
5.  Apply the training and testing split.
6.  Apply SMOTE only to the training data.
7.  Train the four baseline models.
8.  Record the baseline evaluation results.
9.  Run Grid Search and Randomized Search.
10. Perform Five-Fold Cross-Validation.
11. Compare all optimised models.
12. Select the final XGBoost configuration.
13. Run SHAP analysis.
14. Generate the final tables and figures.

Results may vary slightly between environments because of software
versions, hardware, random seeds and implementation details.

## Expected Output

The completed project should produce:

-   Cleaned and prepared modelling data.
-   Balanced training data using SMOTE.
-   Baseline model results.
-   Hyperparameter optimisation results.
-   Five-Fold Cross-Validation results.
-   Accuracy, F1-score and ROC-AUC comparisons.
-   Confusion matrices.
-   ROC curves.
-   Training and prediction time measurements.
-   Memory usage measurements.
-   SHAP feature analysis.
-   Final XGBoost model.
-   Final comparative evaluation.
-   Dissertation results and discussion.

## Conclusion

This project provides a structured framework for bank customer churn
prediction using machine learning and deep learning. Logistic
Regression, Random Forest, XGBoost and ANN were evaluated under
consistent experimental conditions.

The baseline experiments established XGBoost as the strongest initial
model with 84.70 percent accuracy. Hyperparameter optimisation further
improved XGBoost, with the Grid Search configuration achieving 86.25
percent test accuracy. Five-Fold Cross-Validation produced a mean
accuracy of 90.29 percent, supporting the model's consistent performance
across validation folds.

SHAP analysis identified Age, Number of Products, Tenure and Active
Membership as influential churn-related factors, with Age identified as
the most influential feature.

Overall, the Grid Search optimised XGBoost model was selected as the
final model because it provided the strongest overall combination of
predictive performance, validation performance and practical resource
requirements.


## Dataset Source

The dissertation presentation identifies the Kaggle Bank Customer Churn
Prediction Dataset as the dataset source.

For the exact source and licensing conditions, refer to the dataset page
used in the dissertation rather than redistributing the original dataset
without checking its terms.

## Academic Project Note

This repository supports the dissertation project on bank customer churn
prediction. The reported results and methodology should be interpreted
within the experimental scope, dataset characteristics and limitations
documented in the dissertation.

The README is intended to explain the project purpose, workflow,
implementation approach, evaluation process and main findings.

# Data Science and Tech Systems Assignment 1: Predictive Modelling of Eating Out In Sydney

Included in this repository are the following:
1. DSTS Assignment 1 PDF file.
2. DSTS Assignment 1 Jupyter Notebook. This will demonstrate the code and charts used in this project.

This project was coded using Python.

This assignment's instructions and deliverables and a summary of the main outcomes are provided here:

## Assignment Instructions and Deliverables

### Part A – Importing and Understanding Data  
**1 - Provide plots/graphs to support:**
  * How many unique cuisines are served by Sydney restaurants?
  * which suburbs (top-3) have the highest number of restaurants?
  * “Restaurants with ‘excellent’ rating are mostly very expensive while those with ‘Poor’ rating are rarely expensive”. Do you agree on this statement or not? Please support your answer by numbers and visuals.

**2 - Perform exploratory analysis for the variables of the data.** This can be done by producing histograms and distribution plots and descriptive insights about these variables. This can be performed at least for the following variables.  
  * Cost
  * Rating
  * Type

**3 - Produce Cuisine Density Map:** Using the restaurant geographic information and the provided “sydney.geojson” file, write a python function to show a cuisine density map where each suburb is colour-coded by the number of restaurants that serve a particular cuisine. Use Geopandas.   

**4 - Tableau Dashboard for quick insights:** Can you generate a Tableau dashboard that visualise some of the graphs/plots to answer some of the EDA questions above? Also, can you share this dashboard on the Tableau public?  

### Part B – Predictive Modelling
In this part, you are expected to apply predictive modelling to predict/classify the success of the restaurants.  
**I. Feature Engineering:** Implement the feature engineering approaches to:  
1. Perform data cleaning to remove/impute any records that are useless in the predictive task (such as NA, NaN, etc.)  
2. Use proper label/feature encoding for each feature/column you consider making the data ready for the modelling step.  

**II. Regression:**
 3. Build a linear regression model (model_regression_1) to predict the restaurants rating (numeric rating) from other features (columns) in the dataset. Please consider splitting the data into train (80%) and test (20%) sets.  

 4. Build another linear regression model (model_regression_2) with using the Gradient Descent as the optimisation function.  

 5. Report the mean square error (MSE) on the test data for both models.  

**III. Classification:**
 6. Simplify the problem into binary classifications where class 1 contains ‘Poor’ and ‘Average’ records while class 2 contains ‘Good’, ‘Very Good’ and ‘Excellent’ records.  

 7. Build a logistic regression model (model_classification_3) for the simplified data, where training data is 80% and the test data is 20%.
  
 8. Use the confusion matrix to report the results of using the classification model on the test data.
   
 9. Draw your conclusions and observations about the performance of the model relevant to the classes’ distributions.

Bonus: Repeat the previous classification task using three other models of your choice.  

### Part C – Deployment
**Step 1:** Deploy the code on GitLab  
In this step you are required to deploy your source code with its dependencies to a repository and then push this repository to your GitLab account.  

**Step 2:** Deploy a Docker image to the Docker Hub
In this step, you need to create a docker image with all the trained models with the data and code to run these models one after another and produce the results. So, the user who would use this Docker image will be able to see the output results (accuracy, confusion matrix etc.) of applying all the three models on the accompanied data.  

### Deliverables
You are required to submit a compressed (e.g. ZIP) file to the Canvas website of the unit with the following files:  
**1- Python Jupyter Notebook** with the code for parts A & B with all explanation, discussion and insights added as Markdown cells or comments into the notebook(s).  


**2- A PDF document with the following:**  
 a. Link to the Tableau Dashboard.  
 https://public.tableau.com/app/profile/alan.gaugler/viz/DSTS_Ast1/Suburbs?publish=yes  
 b. Results of the (regression and classification) trained models on the test data. These results need to be listed into two tables: one for the regression and another for the classification.  
 c. The list of the commands that you have used to deploy your source code to the GitLab repository.  
 d. The list of the commands that you have used to create and to push the Docker image to the Docker Hub.  
 e. The Link of the source code you have deployed on the GitLab.
 f. The Link of the Docker image you have deployed on the Docker Hub.  

## Project Summary and Main Outcomes

### Key Steps:

#### Data Cleaning and Preprocessing:
- Removed unnecessary features (e.g., addresses, links, latitude/longitude) to simplify the dataset and prevent multicollinearity.
- Engineered features like `number_of_cuisines` and `number_of_types` to enrich the data.

#### Feature Encoding:
- High-cardinality categorical variables (e.g., cuisines and subzones) were target-encoded to reduce complexity while retaining meaningful relationships.
- Continuous features were scaled to standardize the input for modeling.

#### Regression Modeling and Evaluation:
- Various regression models were implemented, including **Linear Regression** and **Stochastic Gradient Descent (SGD)** models.
- Metrics used for evaluation included:
  - **Mean Squared Error (MSE)**: Smaller values indicate better performance.
  - **Mean Absolute Error (MAE)**: Smaller values are preferable.
  - **R² (R-Squared)**: Higher values (up to 1.0) indicate better variance explanation.

#### Hyperparameter Tuning:
- Randomized search and cross-validation (10-fold repeated three times) were used to optimize the SGD models.

#### Main Findings:
- **Linear Regression** outperformed all other models, achieving the lowest MSE and MAE while having the highest R² score.
- Stochastic Gradient Descent models showed similar performance to Linear Regression but did not surpass it, even after hyperparameter tuning.
- Feature engineering and target encoding significantly improved model interpretability and performance.

#### Classification Modeling:
- Classified restaurant ratings into categories using models like Logistic Regression.
- Metrics used for evaluation included:
  - **Accuracy:** Indicates the overall correctness of predictions.
  - **Precision:** Measures the proportion of correctly identified positive instances.
  - **Recall:** Measures the ability to capture all positive instances.
- To ensure meaningful evaluation, highly correlated features were excluded to avoid artificially inflated accuracy.

#### Main Findings:
- Logistic Regression was used to classify restaurant ratings, achieving competitive performance across all metrics.
- Removing highly correlated features ensured the models were robust and generalizable.
- Both regression and classification models provided actionable insights into the factors influencing restaurant ratings and performance.

**Conclusion:**
The project highlights the importance of preprocessing, feature engineering, and careful model evaluation in deriving insights from data. Linear Regression and Logistic Regression emerged as effective tools for this dataset, enabling predictions and classifications that could inform restaurant strategies and customer engagement.


# Employee Promotion Prediction

## Introduction:
This project uses a Random Forest Classification model to predict whether an employee is likely to receive a promotion based on historical employee performance and workplace metrics. The objective is to identify the factors that contribute most to promotion decisions while demonstrating a complete machine learning workflow from data preparation through model evaluation.

Data Source: employee_promotion_predictive.csv

## Objective:

The goal of this project is to build a machine learning model capable of predicting employee promotions using workplace performance indicators. The project also analyzes which employee characteristics have the greatest influence on promotion outcomes.

## Plan of Action
1. Import required Python libraries
2. Load the dataset
3. Clean the data
4. Explore the data
5. Prepare the Data
6. Split the data
7. Build a Random Forest Model
8. Evaluate model performance using
9. Visualize:
- Distribution of promotions
- Feature importance

## Exploring the data
Before training the model, I explored the dataset to understand its structure, identify any data quality issues, and determine whether preprocessing was necessary. The dataset contained 2,500 employee records with six numerical features: Age, Experience Years, Performance Rating, Training Hours, Projects Completed, and Attendance Percentage.

A review of the data showed that the dataset was already clean and well-structured, requiring very little preprocessing. The numerical features contained complete values and consistent ranges, allowing me to move directly into exploratory analysis and model preparation.

<img width="350" height="250" alt="DF19E2D8-4885-45BF-A0EB-515AC6D7F03F_1_201_a" src="https://github.com/user-attachments/assets/c1bd1db5-06b9-4d7d-8fc2-a37fb28d04b2" />

<br><br>
Using the describe function, we were able to understand the distribution of each feature. 
<br>
<img width="800" height="300" alt="2BFE5A2A-AC0F-4285-B0FE-6B70488B30CD_1_201_a" src="https://github.com/user-attachments/assets/53bbe9e9-ec22-4f94-a46e-bf2038f3e7fb" />
<br><br>
The average employee was 39 years old with approximately 10 years of experience. Employees completed an average of 8 projects and attended about 53 hours of training. The average performance rating was 3.02 out of 5, indicating that most employees were performing at a moderate level. Attendance was generally high, averaging 85.3%, with values ranging from 70% to 100%. The minimum and maximum values for each feature fell within realistic ranges, suggesting there were no obvious data entry errors or extreme outliers that required additional cleaning.

<br><br>
<img width="500" height="400" alt="5CFDC4D1-8740-4070-95DD-131BD0FC5A42_1_201_a" src="https://github.com/user-attachments/assets/848b11d9-bf2e-4198-a6c6-a6e6e7bf98b4" />
<br><br>
I examined the distribution of the target variable using a bar graph or value counts. This will help determine whether promoted and non-promoted employees were represented equally. Understanding the class distribution is important because an imbalanced dataset can influence model performance and evaluation metrics.
Although the graoh of promoted and non-promoted employees is close, the non-prompted employees are defentily leading by about 30%. 
<br><br>
<img width="500" height="400" alt="8AC763DF-EC5C-49D4-B36E-5B491EC93A47_1_201_a" src="https://github.com/user-attachments/assets/7707d1ad-fba0-4ecd-8bf5-7f24e2c8b013" />
<br><br>
Based on the correlation heatmap, the most obvious positive correlation is Age and Years of Expereince at 0.82 because older employees typically have more work experience. The next most telling correlation to Promotion was Projects Completed at 0.61 before Years of Expereince(0.37) and Performance Rating(0.35). While correlation alone does not determine feature importance, these results provide a strong starting point for model development. By emphasizing the variables most closely associated with promotion, the Random Forest model can evaluate how these factors contribute to prediction accuracy alongside the remaining employee characteristics. 
<br><br>
##Prepare the Data

Before training the model, I separated the dataset into feature variables (x) and the target variable (y). The target column, Promotion, originally contained categorical values ("Yes" and "No"), so I encoded them into binary values:

Yes → 1
No → 0

##Split the Data
Checked for duplicates before training.
Eventhough this dataset was clean and well-structured, we want can check for duplicates and dataset shape to help determine the best test/train split. 
<br><br>
<img width="587" height="341" alt="Screenshot 2026-07-11 at 2 16 43 PM" src="https://github.com/user-attachments/assets/074869c9-4aa3-48ce-b185-9d3163d73639" />
<br><br>
Considering that there were no duplicates and the shape of the dataset was (2500,7), it was safe to assumne a traditional 80/20 split would be a the ideal way to train this model.
Along with that, using a random state of 42 ensures the results are reproducible.

##Build a Random Forest Model

Before creating the model, I evaluated several values for n_estimators. As shown in the graph below, I found that model accuracy stabilized around 77 trees. Increasing the number of trees beyond this point produced little improvement while increasing training time, so 77 was selected as the final n-estimator value.

<img width="640" height="501" alt="Screenshot 2026-07-11 at 2 39 49 PM" src="https://github.com/user-attachments/assets/009d551d-5bf8-4dce-a6d5-8a14793407a7" />

After determining the best n-estimator, I was able to create a model using Random Forest Classifier. Once that is complete, I was able to fit the model to the feature and target training data. Now that the training is complete, I used the model to predict promotion outcomes for employees in the testing dataset. These predictions were then compared to the actual promotion outcomes to measure the model's performance.
<br><br>
##Evaluating Model Performance
In order to evealuate the final performance of this model, I generated an accuracy score, confusion matrix, and classfiication report which includes the precision, recall, and f1 score.
<br><br>
###Accuracy:
Using the target test and target prediction set, we were able to generate an accuracy score for the model. The model showed a score of 96.2% which exceeds the baseline score of 95%. Hence classifying this model as above accurate. 

###Confusion Matrix
Based on the confusion matrix, this model 

###Classification Report:
I initially generated a confusion matrix which shows a highly accurate binary classification model that correctly predicted 481 out of 500 total instances which exhibits balanced, strong performance across both categories. This aligns with the accuracy score that was generated. 
Next I generated a classification report which shows precision, recall, and f1 score. All of these scores produced a result of 96.2%. 
<br><br>
<img width="542" height="173" alt="Screenshot 2026-07-11 at 3 04 32 PM" src="https://github.com/user-attachments/assets/9282d809-af14-4a73-83f3-40f2e5bb0f22" />
<br><br>
These metrics provide a more complete assessment than accuracy alone by showing how effectively the model identifies both promoted and non-promoted employees.

##Feature Importance
-importance
<img width="345" height="256" alt="Screenshot 2026-07-11 at 3 33 55 PM" src="https://github.com/user-attachments/assets/b44df647-9a66-4f51-bbc3-8ee2ee60f3db" />

-graph
<img width="769" height="429" alt="Screenshot 2026-07-11 at 3 33 59 PM" src="https://github.com/user-attachments/assets/3ffb2e87-0a24-4efb-8f87-c8ef0cd4374b" />


##Key Findings




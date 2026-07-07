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
5. Convert the target variable
6. Select the predictor variables
7. Split the data
8. Train a Random Forest Classifier
9. Generate predictions
10. Evaluate model performance using:
- Accuracy
- Confusion Matrix
- Classification Report
10. Visualize:
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

The average employee was 39 years old with approximately 10 years of experience. Employees completed an average of 8 projects and attended about 53 hours of training. The average performance rating was 3.02 out of 5, indicating that most employees were performing at a moderate level. Attendance was generally high, averaging 85.3%, with values ranging from 70% to 100%. The minimum and maximum values for each feature fell within realistic ranges, suggesting there were no obvious data entry errors or extreme outliers that required additional cleaning.


<img width="500" height="400" alt="5CFDC4D1-8740-4070-95DD-131BD0FC5A42_1_201_a" src="https://github.com/user-attachments/assets/848b11d9-bf2e-4198-a6c6-a6e6e7bf98b4" />

I examined the distribution of the target variable using a bar graph or value counts. This will help determine whether promoted and non-promoted employees were represented equally. Understanding the class distribution is important because an imbalanced dataset can influence model performance and evaluation metrics.
Although the graoh of promoted and non-promoted employees is close, the non-prompted employees are defentily leading by about 30%. 

<img width="500" height="400" alt="8AC763DF-EC5C-49D4-B36E-5B491EC93A47_1_201_a" src="https://github.com/user-attachments/assets/7707d1ad-fba0-4ecd-8bf5-7f24e2c8b013" />








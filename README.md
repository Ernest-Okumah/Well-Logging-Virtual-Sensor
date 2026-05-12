# Well Logging Virtual Sensor: Predicting Compensated Neutron Logs

## Introduction
In oil and gas exploration, well logging is an important technique used to evaluate subsurface formations and determine reservoir properties. Logging tools measure various physical properties of rocks and fluids inside a wellbore. One important logging tool is the Compensated Neutron Log (CNL), which measures hydrogen concentration in the formation and is commonly used to estimate porosity. 

However, logging tools sometimes experience hardware failures, which can lead to missing measurements. To solve this problem, a virtual sensor can be developed using machine learning. A virtual sensor predicts the value of a missing measurement using other available logging data. In this project, machine learning algorithms in Orange were used to predict the Compensated Neutron Log from other well logging measurements.

## Dataset
The dataset used in this project was obtained from Kaggle. The dataset contains measurements from well logging operations, providing information about rock properties and reservoir characteristics. 

The variables in the dataset include:
* **Photoelectric Factor (PEF)**: Measures the interaction between gamma rays and formation materials and helps identify rock type.
* **Gamma Ray Log (GR)**: Measures natural radioactivity of formations and helps distinguish shale from clean formations.
* **Access Controller**: Represents control or resistivity-related measurements from the logging tool.
* **Density Log**: Measures the bulk density of the formation and is used to estimate porosity.
* **Compensated Neutron Log (CNL)**: Measures hydrogen concentration in the formation and indicates porosity. 

The Compensated Neutron Log (CNL) was assigned as the target variable for prediction. The remaining variables (PEF, GR, Access Controller, and Density Log) were selected as input features.

## Methodology
The analysis was performed using Orange Data Mining, a visual programming tool for machine learning and data mining. 

### Data Cleaning and Preprocessing
* Missing numerical values were replaced using the mean value of the respective variable.
* This approach ensures that all records remain usable while maintaining the overall distribution of the data.
* The data was normalized to a common range between 0 and 1. 
* By normalizing the data, no single variable dominates the learning process due to its larger magnitude.

### Modeling and Evaluation
Five different regression algorithms were selected and implemented to ensure a comprehensive evaluation of model performance. These algorithms include:
* Linear Regression
* Regression Tree
* Random Forest
* k-Nearest Neighbours (kNN)
* Support Vector Regression (SVR)

The models' performances were evaluated using 10-fold cross-validation. The models were evaluated using key performance metrics, including Root Mean Square Error (RMSE), Mean Absolute Error (MAE), and Coefficient of Determination (R²).

## Results
The results showed clear differences in the performance of the five models. 
* **Best Model**: Random Forest achieved the best overall performance, with the lowest RMSE (2.178) and MAE (1.277), and the highest R² value (0.948). This indicates that Random Forest provided the most accurate predictions and was able to capture the relationship between the input variables and the target variable effectively.
* **Moderate Performers**: The k-Nearest Neighbours (kNN) and Regression Tree models also performed reasonably well, with R² scores of 0.922 and 0.915 respectively. 
* **Poor Performers**: Support Vector Machine (SVM) and Linear Regression showed poor performance, with significantly higher RMSE values (62.06 and 79.15 respectively) and low R² values (0.308 and 0.118).

## Conclusion
This project highlights the importance of data preprocessing, model selection, and evaluation in building accurate predictive models. The evaluation results indicate that ensemble methods such as Random Forest are more suitable for this type of regression problem, as they can handle complex relationships within well logging data more effectively than simpler models. Ultimately, the use of machine learning as a virtual sensor provides a practical solution for handling missing logging data and can support better decision-making in reservoir analysis.

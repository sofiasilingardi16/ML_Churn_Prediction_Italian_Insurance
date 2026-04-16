# ML Churn Prediction in Italian Insurance

## Project Overview
This project aims to develop a machine learning model to predict customer churn in the Italian motor insurance industry. By utilizing customer data, we can identify factors that lead to customer retention or loss, allowing for better marketing strategies and customer engagement.

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
4. [Results](#results)
5. [Usage](#usage)
6. [Conclusion](#conclusion)

## Introduction
Customer churn refers to the phenomenon of customers ceasing to use a company's services or products. In the insurance sector, predicting which customers are likely to churn can significantly impact profitability and customer satisfaction.

## Dataset
- **Source**: The dataset is sourced from [source link or description].
- **Features**: The dataset contains various features such as:
  - Customer ID  
  - Age  
  - Gender  
  - Policy details  
  - Claims history  
  - Tenure

## Methodology
1. **Data Preprocessing**: Cleaning and transforming the data to ensure quality input for the model.
2. **Feature Engineering**: Selecting and constructing features that can improve model performance.
3. **Model Selection**: Testing multiple algorithms to find the best fit (e.g., Logistic Regression, Decision Trees, Random Forest).
4. **Model Training and Evaluation**: Splitting data into training and test sets, training the model, and evaluating performance using metrics like accuracy, precision, recall, and F1 score.

## Results
- **Best Performing Model**: The model with the highest accuracy was the Random Forest classifier.
- **Key Insights**: Analysis on which features had the most influence on churn prediction.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/sofiasilingardi16/ML_Churn_Prediction_Italian_Insurance.git
   ```
2. Install required libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the model:
   ```bash
   python churn_prediction.py
   ```

## Conclusion
The project highlights the importance of data-driven approaches in insurance and how machine learning can be leveraged to improve customer retention efforts. Future work will include exploring advanced models and real-time prediction capabilities. 

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
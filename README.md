# Data Mining Final Project: San Francisco Salaries Analysis

This project explores the San Francisco employee salary dataset to uncover insights and trends related to employee compensation.

## Data Overview

The dataset contains information on salaries, job titles, benefits, and other attributes for San Francisco city employees. 

## Analysis and Insights

The analysis focuses on:

- **Exploring Data Distributions:** Understanding the distributions of salary components like BasePay, OvertimePay, Benefits, and TotalPay.
- **Job Title Analysis:** Categorizing job titles into general categories for better analysis and understanding pay differences.
- **Pay Trends by Year:** Analyzing salary trends across different years.
- **Gender Pay Gap:** Investigating potential gender-based pay disparities.
- **Top Earning Jobs:** Identifying job groups with the highest total pay.
- **Correlation Analysis:** Examining correlations between different salary components.
- **Predictive Modeling:** Building a linear regression model to predict BasePay based on other factors.
- **Classification Modeling:** Applying Logistic Regression and Random Forest to classify employee gender based on salary and job features.

## Key Findings

- **Pay Variations:** There are significant variations in pay across different job titles and years. 
- **Gender Pay Gap:** Evidence suggests potential pay discrimination based on gender, with men generally earning more in most job groups.
- **Top Earning Jobs:**  Firefighters, Police Officers, and Medical Professionals tend to have the highest total pay.
- **Correlation:** Strong correlations exist between salary components, highlighting the influence of overtime and other pay on total compensation.
- **Predictive Modeling:** The linear regression model can reasonably predict BasePay based on selected input features.
- **Classification Modeling:** Both Logistic Regression and Random Forest models show reasonable accuracy in classifying employee gender.

## Libraries Used

- `numpy`: For numerical computation
- `pandas`: For data manipulation and analysis
- `seaborn`: For statistical data visualization
- `plotly`: For interactive data visualization
- `gender-guesser`: For gender detection
- `scikit-learn`: For machine learning tasks

## Running the Code
 **Install Required Libraries:**
    ```bash
       pip install numpy pandas matplotlib seaborn plotly gender-guesser scikit-learn cufflinks

## Conclusion

This analysis provides insights into the San Francisco employee salary data, highlighting pay variations, potential gender-based pay discrepancies, and correlations between salary components. The predictive and classification models showcase the applicability of machine learning techniques to understand and potentially mitigate pay disparities.

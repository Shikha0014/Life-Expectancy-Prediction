# Life-Expectancy-Prediction
Global life expectancy prediction using Linear Regression.

## Introduction
The Life Expectancy (WHO) dataset provides comprehensive information on life expectancy
trends and related indicators across countries from 2000-2015.<br>
The dataset covers a wide range of continuous variables, including our target variable
average life expectancy, and other continuous variables like GDP per capita, education
levels, mortality rates, and health-related behaviors like alcohol consumption. The
data is structured to allow for comparisons between developed and developing countries, as
well as analysis of the relationships between different socioeconomic and health factors.<br>
Using this rich information, the analysis provided in this report tries to shed light on the
complex processes driving global life expectancy trends, uncover significant correlations
and discrepancies, and attempt to utilise a Linear Regression Model to determine
whether any parameters can predict life expectancy.

## Predictive Modelling
To begin the predictive modelling section, we look at what factors influence the prediction of
average life expectancy. The Pearson Correlation heatmap shows the correlation of
different variables in the dataset.<br>
**Schooling has the strongest correlation (0.75) with life expectancy.** This shows that
increasing educational attainment could be a significant factor in predicting and boosting life
expectancy.<br>
**Other Positive Correlates:** GDP (0.46) and income composition of resources (0.72) have
relatively substantial positive correlations with the target variable. These socioeconomic
indicators should be included as potential predictors in the regression model.<br>
**Negative Correlates:** Adult mortality (-0.70) has the highest negative association with life
expectancy. This health indicator should be considered a significant explanatory variable in
the model.<br>
To predict the target variable “Average Life Expectancy” we will employ three different
Linear Regression techniques and compare the performance of these techniques using
below metrics,<br>
1. MSE (Mean Squared Error)
2. RMSE (Root Mean Squared Error)
3. MAE (Mean Absolute Error)
4. MAPE (Mean Absolute Percentage Error)
5. r2_Score (R-Squared Score)

## Method 1 (Simple Linear Regression)
In this method we take **the highest correlated variable (Schooling - 0.75)** to predict the target variable (Average Life Expectancy).<br>
To create the Linear Regression model for all the methods and calculate the above performance metrics I have used the Scikit-Learn library in Python.
## Method 2 (Multi Linear Regression)
In this method we take the 5 most highly correlated variables **(Adult Mortality, BMI, HIV/AIDS, Income composition of resources, Schooling)** to predict the target variable (Average Life Expectancy).
## Method 3 (Multi Linear Regression using Z-Score Standardisation)
In this method we take the 5 most highly correlated variables (Adult Mortality, BMI, HIV/AIDS, Income composition of resources, Schooling) and then scale them using Z-Score to predict the target variable (Average Life Expectancy).<br>

**To Scale using Z-Score I used the StandardScaler function in Scikit-Learn.**<br>

Across the major evaluation criteria (MSE, RMSE, MAE, and MAPE), the more sophisticated models, Multiple Linear Regression and Scaled Multiple Linear Regression, consistently outperform the simpler Simple Linear Regression. Simple Linear Regression has wider gaps between train and test scores, indicating probable overfitting and poorer generalisation than the other two models. Multiple Linear Regression and Scaled Multiple Linear Regression, on the other hand, have less disparities between training and testing, implying that they can reduce errors and retain performance on unseen data. Overall, the analysis shows that sophisticated regression techniques outperform the basic linear model in terms of predictive ability.<br>

**The r2_Scores for Multiple Linear Regression Model using Z-Score Standardisation**
1. Test R2 Score - 0.82
2. Train R2 Score - 0.79

## Conclusion
### Key Correlates

1. Education (measured as average years of schooling) has the highest positive correlation with life expectancy at 0.75. This reinforces the critical role of education in enhancing health outcomes.
2. Adult mortality shows a significant negative correlation at -0.70, underlining the need for health interventions to reduce premature deaths.
3. Economic factors like GDP and income composition of resources also exhibit strong positive associations (0.46 and 0.72, respectively).

### Disparities
1. Developed nations consistently exhibit a higher average life expectancy than developing nations, with a 10–15 year median gap. The lowest life expectancies (e.g., Sierra Leone at <55 years) highlight persistent health inequities, particularly in Sub-Saharan Africa.
2. Education and alcohol consumption patterns demonstrate that investment in education could yield multifaceted health benefits, especially in developing nations.

### Predictive Model Performance
1. Multiple Linear Regression and Scaled Multiple Linear Regression models achieved superior predictive accuracy, with an R² score of 0.82 for testing data.
2. The models effectively reduced overfitting compared to Simple Linear Regression, indicating their robustness in capturing the relationships among the variables.
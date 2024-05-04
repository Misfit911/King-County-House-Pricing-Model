# King County House Pricing Model
***

![Interstate 5 North - King County South - AARoads - Washington](Interstate%205%20North%20-%20King%20County%20South%20-%20AARoads%20-%20Washington.jpeg)

## Overview
### Project Focus
Our real estate project focuses on empowering homeowners in northwestern King County by providing actionable insights for buying and selling homes.

### Goals
- **Empowerment:** Equip homeowners with the insights and tools needed to navigate the real estate market confidently.
- **Value Optimization:** Maximize the value of properties through innovative strategies and personalized guidance.
- **Transparency:** Provide transparent and data-driven insights to ensure informed decision-making for both buyers and sellers.

### Significance
In a rapidly evolving real estate market like King County, informed decision-making is key to success. Our project aims to revolutionize the home buying and selling experience by leveraging data-driven insights and innovative approaches.

## The Business Problem
- **Understanding the Market Dynamics**
- **Lack of Actionable Insights:** Many homeowners struggle to determine the optimal pricing strategies for their properties.
- **Uncertainty for Home Buyers:** They often lack guidance on the approximate price of houses that align with their desired features and budget.

## Data Understanding
**Data Source:** Our primary dataset, the King County House Sales dataset, serves as the foundation of our analysis. This dataset contains information on various properties sold in King County, Washington. It includes details such as property features, sale prices, and sales history. This dataset is central to our analysis as it provides insights into the factors influencing house prices in the area. [Link Here](https://www.kaggle.com/datasets/doesnotcompile/nf-kc-house-data)

### Results
What features affect Price
![alt text](image-3.png)
`sqft_living`, `sqft_above`, `sqft_living15`, `bedrooms`, `bathrooms`, `grade`, `waterfront` affect price and lead to high price

**Simple Linear Regression**

**Model 1**
![alt text](image-2.png)
The R-squared of this model is 0.404 which means the model explains about 40.4% of the variance in the target variable (price) which is not that great.

**Multiple Linear Regression**

**Model 2**

The R-squared value is 0.540, indicating that approximately 54% of the variance in housing prices is explained by the independent variables included in the model.

1. **bedrooms**: Each additional bedroom is associated with a decrease in housing prices by approximately $47,910, holding other variables constant.
2. **bathrooms**: Each additional bathroom is associated with an increase in housing prices by approximately $51,560, holding other variables constant.
3. **floors**: Each additional floor is associated with an increase in housing prices by approximately $68,110, holding other variables constant.
4. **condition_rating**: Each unit increase in the condition rating is associated with an increase in housing prices by approximately $22,990, holding other variables constant.

> **Model 3**

>The R-squared of the model is 0.738 which explains 73.8% of the variance in housing prices which is an improvement compared to the first and the second model.

>**Model 4**

>Logarithmic transformation. The R-squared of this model is 0.784 which means the model explains 78.4% is higher than the R-squared of the previous model model 3.

>Normality Test after Log Transformation

>This test suggests that the residuals after logarithmic transformation the distribution of the residuals was homoskedastic.

>Model 3 has a higher RMSE of `172221.2583885908` compared to Model 4 which has a RMSE of `0.3022692781936056`. In general, a lower RMSE (Root Mean Squared Error) indicates better predictive performance of the model. A lower RMSE suggests that the model's predictions are closer to the actual values on average. This indicates better accuracy in estimating the target variable.

> Therefore our best pick would be the `Log-Transformed Multiple Linear Regression Model`.

### Log-Transformed Regression Results
1. The average price of a house is $150K
2. Houses with a waterfront have a 33% higher price than houses with no waterfront
3. Houses with excellent views have a 14% higher price than houses with average views.
4. Houses with very good conditions have an 11% higher price compared to houses with average conditions
5. One additional bathroom will result in a 7% increase in price
6. Houses with 2 bedrooms have a 4% increase in price than houses with one bedroom; however, houses with more than 4 bedrooms have a decrease in price compared to houses with one bedroom
7. The higher the grade the higher the price as houses with grade 12 (Luxury) have a 100% higher price than houses with grade 5 (Fair)
8. Houses in Medina city have the highest price, 62% higher than houses in Seattle
9. Houses in Mercer Island have a 25% higher price and houses in Bellevue have a 16% higher price

## Recommendations
1. We recommend prioritizing investments or improvements that enhance the square footage of living space. Given its strong correlation with house prices, increasing the living space of a property could significantly boost its value.
2. Upgrade property grades to enhance market appeal. Highlight proximity to amenities and waterfront locations in marketing efforts.
3. Consider renovations to improve overall property grade and desirability. Emphasize lifestyle benefits to attract buyers and justify premium pricing. Focus on key factors such as living space, property grade, amenities, and location to realize the full property potential in the King County market.

## Conclusions
### In addition to the insights gathered, the analysis has some limitations:
1. The dataset used for this analysis was limited to a specific geographic area and time period. It may not be representative of other locations or time periods, which could limit the generalizability of the results.
2. The data in the dataset is from 2014 and 2015. Therefore, it may not be able to account for changes in the housing market since then. As a result, the model may not accurately predict the value of a house in 2024.
3. While the model can identify relationships between variables, it cannot prove causality. Therefore, it's important to be cautious about making causal claims based solely on the results of this model.
4. Overall, the analysis provides valuable insights for homeowners, real estate professionals, and potential buyers interested in the King County housing market. By understanding the key factors affecting house prices and acknowledging the limitations of the analysis, stakeholders can make informed decisions regarding pricing strategies, property enhancements, and investment opportunities. Further research and analysis may be warranted to explore additional factors or refine existing models for better predictive accuracy and actionable insights.

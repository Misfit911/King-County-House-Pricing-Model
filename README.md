<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>King County House Pricing Model</title>
</head>
<body>
    <h1>King County House Pricing Model</h1>
    <hr>
    <p align="center">
        <img src="Interstate 5 North - King County South - AARoads - Washington.jpeg" alt="Interstate 5 North - King County South - AARoads - Washington" width="700" height="450">
    </p>

<h1>Overview</h1>
    <h3>Project Focus</h3>
    <p>Our real estate project focuses on empowering homeowners in northwestern King County by providing actionable insights for buying and selling homes.</p>
    <h3>Goals</h3>
    <ul>
        <li>Empowerment: Equip homeowners with the insights and tools needed to navigate the real estate market confidently.</li>
        <li>Value Optimization: Maximize the value of properties through innovative strategies and personalized guidance.</li>
        <li>Transparency: Provide transparent and data-driven insights to ensure informed decision-making for both buyers and sellers.</li>
    </ul>

<h3>Significance</h3>
    <p>In a rapidly evolving real estate market like King County, informed decision-making is key to success. Our project aims to revolutionize the home buying and selling experience by leveraging data-driven insights and innovative approaches.</p>

<h1>The Business Problem</h1>
    <ul>
        <li>Understanding the Market Dynamics</li>
        <li>Lack of Actionable Insights: Many homeowners struggle to determine the optimal pricing strategies for their properties.</li>
        <li>Uncertainty for Home Buyers: They often lack guidance on the approximate price of houses that align with their desired features and budget.</li>
    </ul>

<h1>Data Understanding</h1>
    <p>Data Source: Our primary dataset, the King County House Sales dataset, serves as the foundation of our analysis. This dataset contains information on various properties sold in King County, Washington. It includes details such as property features, sale prices, and sales history. This dataset is central to our analysis as it provides insights into the factors influencing house prices in the area. <a href="https://www.kaggle.com/datasets/doesnotcompile/nf-kc-house-data">Link Here</a></p>

<h2>Results</h2>
    <p>What features affect Price</p>
    <p><img src="image.png" alt="How features affect price"></p>
    <p><code>sqft_living</code>, <code>sqft_above</code>, <code>sqft_living15</code>, <code>bedrooms</code>, <code>bathrooms</code>, <code>grade</code>, <code>waterfront</code> affect price and lead to high price</p>

<h3><strong>Simple Linear Regression</strong></h3>
    <p><strong>Model 1</strong></p>
    <p><img src="image-1.png" alt="Model 1"></p>
    <p>The R-squared of this model is 0.404 which means the model explains about 40.4% of the variance in the target variable (price) which is not that great.</p>

<h3><strong>Multiple Linear Regression</strong></h3>
    <p><strong>Model 2</strong></p>
    <p>The R-squared value is 0.540, indicating that approximately 54% of the variance in housing prices is explained by the independent variables included in the model.</p>
    <ol>
        <li><strong>bedrooms</strong>: Each additional bedroom is associated with a decrease in housing prices by approximately $47,910, holding other variables constant.</li>
        <li><strong>bathrooms</strong>: Each additional bathroom is associated with an increase in housing prices by approximately $51,560, holding other variables constant.</li>
        <li><strong>floors</strong>: Each additional floor is associated with an increase in housing prices by approximately $68,110, holding other variables constant.</li>
        <li><strong>condition_rating</strong>: Each unit increase in the condition rating is associated with an increase in housing prices by approximately $22,990, holding other variables constant.</li>
    </ol>

<p><strong>Model 3</strong></p>
    <p>The R-squared of the model is 0.738 which explains 73.8% of the variance in housing prices which is an improvement compared to the first and the second model.</p>

<p><strong>Model 4</strong></p>
    <p>Logarithmic transformation. The R-squared of this model is 0.784 which means the model explains 78.4% is higher than the R-squared of the previous model model 3.</p>

<p>Normality Test after Log Transformation</p>

<p>This test suggests that the residuals after logarithmic transformation the distribution of the residuals was homoskedastic.</p>

<p>Model 3 has a higher RMSE of <code>172221.2583885908</code> compared to Model 4 which has a RMSE of <code>0.3022692781936056</code>. In general, a lower RMSE (Root Mean Squared Error) indicates better predictive performance of the model. A lower RMSE suggests that the model's predictions are closer to the actual values on average. This indicates better accuracy in estimating the target variable.</p>
    <blockquote>
        Therefore our best pick would be the <code>Log-Transformed Multiple Linear Regression Model</code>.
    </blockquote>

<h2>Regression Results</h2>
    <ol>
        <li>The average price of a house is $150K</li>
        <li>Houses with a waterfront have a 33% higher price than houses with no waterfront</li>
        <li>Houses with excellent views have a 14% higher price than houses with average views.</li>
        <li>Houses with very good conditions have an 11% higher price compared to houses with average conditions</li>
        <li>One additional bathroom will result in a 7% increase in price</li>
        <li>Houses with 2 bedrooms have a 4% increase in price than houses with one bedroom; however, houses with more than 4 bedrooms have a decrease in price compared to houses with one bedroom</li>
        <li>The higher the grade the higher the price as houses with grade 12 (Luxury) have a 100% higher price than houses with grade 5 (Fair)</li>
        <li>Houses in Medina city have the highest price, 62% higher than houses in Seattle</li>
        <li>Houses in Mercer Island have a 25% higher price and houses in Bellevue have a 16% higher price</li>
    </ol>

<h2>Recommendations</h2>
    <ol>
        <li>We recommend prioritizing investments or improvements that enhance the square footage of living space. Given its strong correlation with house prices, increasing the living space of a property could significantly boost its value.</li>
        <li>Upgrade property grades to enhance market appeal. Highlight proximity to amenities and waterfront locations in marketing efforts.</li>
        <li>Consider renovations to improve overall property grade and desirability. Emphasize lifestyle benefits to attract buyers and justify premium pricing. Focus on key factors such as living space, property grade, amenities, and location to realize the full property potential in the King County market.</li>
    </ol>

<h2>Conclusions</h2>
    <h3>In addition to the insights gathered, the analysis has some limitations:</h3>
    <ol>
        <li>The dataset used for this analysis was limited to a specific geographic area and time period. It may not be representative of other locations or time periods, which could limit the generalizability of the results.</li>
        <li>The data in the dataset is from 2014 and 2015. Therefore, it may not be able to account for changes in the housing market since then. As a result, the model may not accurately predict the value of a house in 2024.</li>
        <li>While the model can identify relationships between variables, it cannot prove causality. Therefore, it's important to be cautious about making causal claims based solely on the results of this model.</li>
        <li>Overall, the analysis provides valuable insights for homeowners, real estate professionals, and potential buyers interested in the King County housing market. By understanding the key factors affecting house prices and acknowledging the limitations of the analysis, stakeholders can make informed decisions regarding pricing strategies, property enhancements, and investment opportunities. Further research and analysis may be warranted to explore additional factors or refine existing models for better predictive accuracy and actionable insights.</li>
    </ol>
</body>
</html>

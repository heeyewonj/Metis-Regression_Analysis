## Regression Analysis: Predicting NYC Apartment Rental Price

## Abstract 

Many new yorkers left the city after they started working remotely amid the pandemic. The apartment rental prices have been decreased and became less predictive. One of the real estate companies tries to predict the new trend of apartment rental prices in New York City. For the solicit, I scraped the data from a real estate marketplace platform called 'City Realty' for the target (i.e., rental price) and features. With multiple trials with different regression techniques, a Ridge regression explained best the features (i.e., number of bathrooms, square feet, year of building built, distance to a nearby station, borough) and the data; 78% of the data were explained by the ridge regression with 5-fold cross-validation compared to the other regression techniques used. Future studies can improve by adding relevant data such as socioeconomic data per zip code. 

# Design

To predict rental prices (i.e., target) of NYC apartments, I decided relevant features with the target: 1. types of the fee (e.g., broker fee versus no fee), 2. neighborhood, 3. the number of units in the building, 4. year apartment built, 5. the number of available stations, 6. the distance of the nearby station, 7. floor of the building, 8. square feet, 9. the number of amenities in the building, 10. the number of bedrooms. After data cleaning and the regression assumption check, I went through the different types of regression models using simple linear, Ridge (L2) and Lasso (L1) regressions, and k-fold cross-validation. 

## Data

The datasets were scraped from one of the real estate marketplace platforms, City Realty. The target was rental prices. The features include 1. types of the fee (e.g., broker fee versus no fee), 2. neighborhood, 3. the number of units in the building, 4. year apartment built, 5. the number of available stations, 6. the distance of the nearby station, 7. floor of the building, 8. square feet, 9. the number of amenities in the building, 10. the number of bedrooms. Additionally, the address and URL for each apartment were used when I treated missing data and inspected outliers. 

## Algorithm

First, I checked the assumptions for a regression model by looking at the residual distribution and the QQ plot. With any violation of the assumptions, I inspected data points that were suspicious and problematic. From the dataset, I found outliers caused the violation, so I dropped those data points. Afterward, I explored how a potential predictive model could explain better by taking out insignificant variables. This process turned out a set of features to add into the final regression model (i.e., the number of bathrooms, square feet, year of building built, the number of amenities, distance to a nearby station, and borough). However, even though these features predicted the target, the distribution of the target was skewed. After a log transformation, RMSE became much lower, indicating the transformed model is a better fit. Although the model did not have multicollinearity issue, I ran several k-fold CV  that  is power for the performance improvement and to have a possible robust model, I found the best predictive model are both Linear and Ridge regression with 5-fold. Both showed the same r-squared of .723.

## Tools

1. Data manipulation: Numpy, Pandas
2. Visualization: Matplotlib, Seaborn
3. Data Collection: Beautiful Soup and Selenium
4. Data Analysis: Scikit-learn and Statsmodels


## Communication
For codes, they are in the "code" folder and saved chronologically. For the presentation, please find the "slide.pdf" file. 
# Project 2 - Ames Housing Data and Kaggle Challenge

I am part of a firm, SmartConsulting, that has been hired by IA Construction, a developer in Iowa. IA construction is looking to purchase land in Ames, IA as well as possibly in other towns nearby. Before they purchase the land and begin to plan out construction, they need more information about the housing market. IA construction wants to be able to estimate the profit from this project as well as design their construction plans to maximize profit. 

SmartConsulting has assessed IA Construction's problem and assigned me the task of creating a model that will predict the sale price of a single home, which will be used to predict the total revenue. However, other members of my team will be using insights from my model to develop other models to help guide construction choices. 

Specifically, my model will be used as a starting point to help advise what types of home models will be most profitable and to help predict how certain features impact home price. These features include:
- 1 story vs 2 story vs split-level
- SQ Footage (Size of the homes)
- Number of bedrooms
- Number of bathrooms
- Quality of building materials/ material choice
- Adding a basement
- Adding a garage


My team's final recommendations will account for costs, time to sell (desirability) and other factors.



# Data Dictionary
Descriptions of each variable in the Ames Dataset can be found on Kaggle.com: https://www.kaggle.com/competitions/dsi-910-ames-housing-challenge/data
This dataset contains 80 independent variables as well as 1 dependent variable- SalePrice. While some of these variables may be helpful in the development of future models for more specific questions, the following variables were selected for the final model:
- Overall Qual 
- Gr Liv Area 
- Garage Area 
- Garage Cars 
- Total Bsmt SF 
- 1st Flr SF 
- Year Built 
- Full Bath 
- Fireplaces 
- MS SubClass 
- Neighborhood 
- Condition 1
- Exter Qual
- Bsmt Exposure
- Kitchen Qual
- Garage Qual
- Exterior 1st
- Exter Cond
- Bsmt Qual
- Bsmt Cond
- BsmtFin Type 1
- Functional
- Fireplace Qu
- Paved Drive
- Sale Type
- Garage Con


# EDA & Data Cleaning
In the EDA & Data Cleaning Notebook, I conducted exploratory data analysis and data cleaning. In my EDA I noted multiple issues such as missing values and incorrect variable types. I corrected this information in my data cleaning steps. In my EDA section I primarily used visualizations to determine which variables had the strongest relationships with saleprice. These are the variables listed above in the data dictionary.


# Model Development
I created multiple linear regression models. I incorporated different features into different models, attempted to create overfit models and scale them back using regularization, and experimented with which variables to include. In the models I created, features such as Polynomials, and regularization techniques such as LASSO decreased the success of the model (measured in R2 and MSE). 

After finding that adding more features was unhelpful, and a model utilizing every possible column did not perform well, I began to focus on identifying the most significant variables and incorporating them into the model. I then used a stats summary to identify some columns that could be dropped (high p-value) and I removed those from the model. MSE decreased and the r2 of my validation data improved. This was the model I chose which is saved in the Final Model notebook. 


# Analysis
This model performed the best out of every model I developed and tested. I analyzed the performance of this model by performing a train-test-split and then comparing the rsquared values of the training vs testing data. I also calculated and compared the MSEs. After refitting my model on the full dataset, I also calculated the cross-validation score for this model.The metrics I calculated were:
- the r squared of training data = .887
- r squared of .905 for the validation data
- MSE of training data = 715730948.6393995
- The MSE of validation data = 563890073.929552
- The mean cross val score was .87

From these metrics I was able to conclude:

- The model was not overfit
- Bias may be high despite a relatively strong r2 value

While the validation r2 was high compared with other models, since the MSE and r2 of the validation data after the train-test split were higher than the metrics of the training data, it seems likely that there are still opportunities to reduce bias and improve the model without increasing variance and overfitting the model.
In order to more accurately predict total revenue, this model should be refined more to better predict the Sale Price of individual homes. While an r2 of .9 is relatively high, even small improvements can mean more precise predictions which when aggragated across many homes, could translate to differences in the millions.

Some of the variables have a signficant impact on Sale Price.





- Presentation slides
- Any other necessary files (images, etc.)

**Submit a link to your repo in Google Classroom.**



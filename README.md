# Football-Match-Prediction
Using jupyter notebooks along with the [Fifa 2022 World Cup dataset](https://www.kaggle.com/datasets/abecklas/fifa-world-cup) from Kaggle to create a model to predict match outcomes.

## Match.ipynb
Linear regression is used here to predict the number of goals scored by the players in the ```number of goals team1``` column of the dataset. All the columns containing strings, such as ```date``` and ```team1```. The columns containing percentages such as ```possession team1``` have been stripped of their '%' signs and converted to strings. Using linear regression gave better results than using Logistic Regression, Decision Tree Classification as well as Random Forest Regression. This model is mostly useless for actually predicting the outcomes of matches because the amount of data necessary for the model to run would be impossible to collect until the match has not finished. The best example of this is the use of the goals of one team in the model to predict the goals of the other. However, this method proves to be quite effective, having a root mean squared error of **2.698479751873428e-15** units with the test data (created with. ```train_test_split(df, test_size=0.2, random_state = 42)```). 

## RealTime.ipynb
The old dataset was updated and a new column of goal difference was added. Using every variable available in the dataset other than the goals scored columns and the string columns this model was able to accurately predict goal difference with a root mean squared error of **2.219947481370205e-14** with training data and **1.3574094975325184** with test data. The rmse was improved by about **0.01** units by using GridSearchCV and setting ```fit_intercept``` to false.



- Note :Every time these datasets were used to train models, the conceded goals were removed.

## RealTime2.ipynb
Greaty reduced number of variables in dataset by only keeping the "possession team1","possession team2","possession in contest","goal preventions team1","goal preventions team2","forced turnovers team1","forced turnovers team2" and "goalDiff" columns. The root mean squared error was **1.5144935778544149** with training data and **1.5144935778544149** with test data.

 # Football Player Market Value Prediction

## Problem Statement
In the English Premier League, May - July represents a lull period due to the lack of club football. What makes up for it, is the intense transfer speculation that surrounds all major player transfers today. You must have seen "Moneyball", where Peter Brand explains Billy Beane that "Its about getting things down to one number using stats the way we read them (players), we find value in player nobody else can see." Therefore, an important part of negotiations is predicting the fair market price for a player and perhaps perform EDA for this.

## EDA (Important Ones)

1. #### Players in every club and position

    ![clubvsplayers](/figures/clubvsplayers.png)

   -  The bar graph above shows how many players are there in every   club and the variation of player's positions.
        - x axis --> club names
        - y-axis --> total number of players.

    The variation of player position are distinguish by different color in each bars. The colors code for players position is explained on the righ side of the chart.
    `Arsenal , Everton , and Huddersfield have the biggest number of players with 28 players . Burnley has the lowest number of players with 18 players.`

2. #### Distribution of Player's Ages

    ![playerhist](/figures/playerhist.png)

    A typical histogram of players age can be called "Edge Peak Histogram".
    - The edge peak distribution looks like the normal distribution except that it has a large peak at one tail.
    - As it is shown in the histogram, the distribution of age is increased untill it meet the peak point at the age between 25-30. 
    - There is one bar that significanly higher than the others, that is why the histogram above can be calles Edge peak histogram.


3. #### Top 10 Player Market Values (2017-2018)

    ![top10players](/figures/top10players.png)

    - The bar chart above shows the top 10 market value for each player.
        - x-axis --> players name
        - y-axis --> market value

    It appears that Eden Hazard and Paul Pogba have the biggest market value, which is 75. They are followed by Alexis Sanchez on the 3rd position.

<!-- 4. ### Average Market Value of every club

    ![avgmarketvalue](/figures/avgmarketvalue.png)

    - The bar chart above shows sorted average of market value for 
      each club. 
        - x-axis -- club names
        - y-axis -- average market value
    
    It appears that ManCity and Chelsea, which are famous for spending money for a star player have the biggest average market value. They are followed by Totenham on the 3rd position. Burnley, Brighton, and Huddersfield are sitting in the lowest 3. -->

4. #### Most Viewed Players

    ![mostviewdplayers](/figures/mostviewdplayers.png)

    - The bar chart above shows the top 10 most view players.
        - x-axis --> Player names
        - y-axis --> Market value

    It appears that Wayne Rooney has the biggest market value, followed by Paul Pogba and Dele Alli on 2nd and 3rd position.

<!-- 6. ### FPL 10 most valuable players

    ![mostvaluableplayers](/figures/mostvaluableplayers.png)]

    - The bar chart above shows the top 10 highest FPL value for each 
      player.
      - x-axis -- players name
      - y-axis -- FPL value
      
    It appears that Harry Kane has the biggest FPL value, followed by Alexis Sanchez on the 2nd position. As it is shown in the graph above, there are 3 Belgium players that sit in this position, who are Eden Hazard, Kevin de Bruyne, and Romeru Lukaku while the FPL value top 10 position is dominated by foreign players. The only local player who is in this position is only Hary Kane. -->

<!-- 7. ###  Average of FPL value for every club

    ![averageFPL](/figures/averageFPL.png)

    - The bar chart above shows sorted average of FPL value for each  
      club. 
      - x-axis -- club names
      - y-axis -- average FPL value

    It appears that ManCity and Chelsea have the biggest average market value. They are followed by Totenham on the 3rd position and the 3 promoted clubs are sitting in the lowest 3. -->

5. #### Correlation Matrix

    ![correlationmatrix](/figures/correlationmatrix.png)

    - Each square shows the correlation between the variables the variables on each axis. 

    - Values closer to zero means there is no linear trend between the two variables.

    - The close to 1 the correlation is the more positively correlated they are the closer to 1 the stronger the relationship is **larger the number and darker the color the higher the correlation between the two variables.**

6. #### Nationality of Players

    ![nationality](/figures/nationality.png)

    - The bar chart above shows the count of players w.r.t their nationality in the FPL.
        - x-axis --> countries
        - y-axis --> count for players
    
    We can conclude that England has highest i.e. maximum number of players.

## Model Evaluations

There are three primary metrics used to evaluate linear models. These are: 
    
    - Mean absolute error (MAE), 
    - Mean squared error (MSE), and 
    - Root mean squared error (RMSE).

- **MAE:** The easiest to understand. Represents average error

- **MSE:** Similar to MAE but noise is exaggerated and larger errors are “punished”. It is harder to interpret than MAE as it’s not in base units, however, it is generally more popular.

- **RMSE:** Most popular metric, similar to MSE, however, the result is square rooted to make it more interpretable as it’s in base units. It is recommended that RMSE be used as the primary metric to interpret your model.


| Algorithm Used               | R<sup>2</sup> Value |   MAE    |   MSE  |  RMSE    |
|------------------------------|---------------------|----------|--------|----------|
| Linear Regression            |      `0.7057`       | `4.7294` | `44.04` | `6.636` |
| Nearest Neighbour Regression |      `0.4511`       | `6.0111` | `82.16` | `9.064` |
| Support Vector Machine       |      `0.3589`       | `5.4067` | `95.95` | `9.795` |
| Decision Tree Regression     |      `0.5169`       | `5.4298` | `72.30` | `8.503` |
| Random Forest Regression     |      `0.7284`       | `4.3749` | `40.65` | `6.376` |
| Gradient Boosted Regression  |      `0.7598`       | `4.0861` | `35.94` | `5.995` |


## Hyperparameter Tuning
Tuning the parameters to build and choose an optimal model is called hyperparameter tuning. 
1. Choosing from following method for hyperparameter tuning
    - RandomizedSearchCV --> A fast way to hypertune model
    - GridSearchCV--> A slow way to hypertune model

Used RandomizedSearchCV for hyperparameter tuning because it is faster than GridSearchCV.
Shown an example for `RandomFrorestRegressor`.

2. Assigned hyperparameters in form of dictionary for the ForestRegressor
   ```python
    {
    'max_depth': [5, 13, 21, 30],
    'max_features': ['auto', 'sqrt'],
    'min_samples_split': [5, 10, 15, 100],
    'n_estimators': [100, 320, 540, 760, 980, 1200]
    }
   ```
3. Fitted the model using 3 fold cross validation
   ```python
   rf_random.fit(X_train,y_train)
   # Fitting 3 folds for each of 10 candidates, totalling 30 fits
   ```
4. Checking best paramters and best score
   ```python
      rf_random.best_params_
    {
        'max_depth': 21,
        'max_features': 'sqrt',
        'min_samples_split': 5,
        'n_estimators': 1200
    }
    ```
5. Scores after hyperparameter tuning
   
| Algorithm Used               | R<sup>2</sup> Value |   MAE    |   MSE   |  RMSE    |
|------------------------------|---------------------|----------|---------|----------|
| Random Forest Regression     |      `0.7685`       | `4.1569` | `40.01` | `6.325`  |


## Choosing the Best Model

A higher R^2 score determines its a best model, so from the above findings we can conclude that `Gradient Boosted` has higher R<sup>2</sup> score followed by `Random Forest` and `Linear Regression`.

```python
LINEAR REGRESSION : 
r2 score: 74%

NEAREST NEIGHBOUR REGRESSION : 
r2 score: 57%

TREE REGRESSION : 
r2 score: 61%

RANDOM FOREST REGRESSION : 
r2 score: 78%

GRADIENT BOOSTED REFGRESSION : 
r2 score: 80%
```
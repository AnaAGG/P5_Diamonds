# P5_Diamonds


![squema](https://github.com/AnaAGG/P5_Diamonds/blob/main/Images/squema.png)
# Data

## Files

  +  diamonds_train.csv: training set
  +  diamonds_predict.csv: test set
  +  sample_submission.csv: sample submission

## Features  

* **id**: only for test & sample submission files, id for prediction sample identification  
* **price**: price in USD  
* **carat**: weight of the diamond  
* **cut**: quality of the cut (Fair, Good, Very Good, Premium, Ideal)
* **color**: diamond colour, from J (worst) to D (best)
* **clarity**: a measurement of how clear the diamond from worst to best is (I1 , SI2, SI1, VS2, VS1, VVS2, VVS1, IF )
* **x**: length in mm  
* **y**: width in mm  
* **z**: depth in mm  
* **depth**: total depth percentage = z / mean(x, y) = 2 * z / (x + y)  
* **table**: width of top of diamond relative to widest point 

# Workflow 

 1- Correlation matrix: 
 
![corrmatrix](https://github.com/AnaAGG/P5_Diamonds/blob/main/Images/corr.png)

  + Correlation `Price` of the diamond and `carat` weight of the diamond are highly correlated
  + `x` ,    `y` and `z` are correlated with the price.
  + `Depth` and `Table` are weakly correlated with the price of the diamond.
  + `Carat` is one of the main features to predict the price of a diamond.

   I drop the `table` and `depth` columns becasue of a low score in the correlation matrix

 2- Encoding categorical variables  
  

| Cut           | Color   | Clarity  |
|---------------|---------|----------|
| Fair = 1      | E:1     | IF  = 1 |
| Good = 2      | D = 2   | SI2 = 2   |
| Ideal = 3     | F = 3   | SI1 = 3 |
| Premium = 4   | G = 4   | VS2 = 4  |
| Very Good = 5 | H = 5   | VS1 = 5   |
|          | I = 6 |VVS2 = 6       |
|          |J = 7|  VVS1 = 7          |
|        |         |  IF = 8        |

  

 3- Train the model: I used four different models to perform the analysis: 

 The selected score to check the goodness of my models was [ `Mean Squared Error` ](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)

   - [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
   - [DecisionTreeRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)
   - [RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)
   - [KNeighborsRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html)

To perform the analysis and find the best model and estimators I used the [GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html) tool from sklearn 

 3- Predict the price of a based on  diamons' characteristics in the test file
 The final model was: `Random Forest` with the following parameters
  - min_samples_leaf=2
  -  min_samples_split=3                                     
  - n_estimators=300
# P5_Diamonds
![portada](https://www.google.com/imgres?imgurl=http%3A%2F%2Fwww.goldandtime.org%2Ffotos%2F1%2Fdiamantes_naturales_sinteticos_lab_thumb_1280.jpg&imgrefurl=http%3A%2F%2Fwww.goldandtime.org%2Fnoticia%2F82437%2FGoldtime%2FLa-mineria-rechaza-la-superioridad-etica-de-los-diamantes-sinteticos.html&tbnid=-d7SZ9GXDQr2JM&vet=12ahUKEwiDgpC-xYzvAhVO4BoKHQjkBlUQMygFegUIARDLAg..i&docid=UnwdAlAIx_vZjM&w=1280&h=709&q=diamantes&hl=es&safe=active&ved=2ahUKEwiDgpC-xYzvAhVO4BoKHQjkBlUQMygFegUIARDLAg)

# Data
## Files
  -  diamonds_train.csv: training set
  -  diamonds_predict.csv: test set
  -  sample_submission.csv: sample submission

## Features  
- **id**: only for test & sample submission files, id for prediction sample identification  
- **price**: price in USD  
- **carat**: weight of the diamond  
- **cut**: quality of the cut (Fair, Good, Very Good, Premium, Ideal  
- **color**: diamond colour, from J (worst) to D (best)  
**clarity**: a measurement of how clear the diamond is (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best))  
- **x**: length in mm  
- **y**: width in mm  
- **z**: depth in mm  
- **depth**: total depth percentage = z / mean(x, y) = 2 * z / (x + y)  
- **table**: width of top of diamond relative to widest point 

# Stepwise 
 1- Correlation matrix: (see also the pairplot)
  - Correlation `Price` of the diamond and `carat` weight of the diamond are highly correlated (> 0.96)
  - `x` , `y` and `z` are correlated with the price.
  - `Depth` and `Table` are weakly correlated with the price of the diamond.
  - `Carat` is one of the main features to predict the price of a diamond.

 2- Train the model: I used four different models to perform the analysis: 

 The selected score to check the goodness of my models was [`Mean Squared Error`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)

   - [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
   - [DecisionTreeRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)
   - [RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)
   - [KNeighborsRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html)

To perform the analysis and find the best model and estimators I used the [GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html) tool from sklearn 

 3- Predict the price of a given diamons' characteristics
 The final model was: PONER EL MODELO QUE USE AL FINAL

Results for the best model:

                


 

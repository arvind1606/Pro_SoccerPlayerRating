# Pro_SoccerPlayerRating

In this project we are going to predict the overall rating of soccer player based on their attributes 

Below is the list of all columns/ features

All Columns:
    ['id', 'player_fifa_api_id', 'player_api_id', 'date', 'overall_rating',
           'potential', 'preferred_foot', 'attacking_work_rate',
           'defensive_work_rate', 'crossing', 'finishing', 'heading_accuracy',
           'short_passing', 'volleys', 'dribbling', 'curve', 'free_kick_accuracy',
           'long_passing', 'ball_control', 'acceleration', 'sprint_speed',
           'agility', 'reactions', 'balance', 'shot_power', 'jumping', 'stamina',
           'strength', 'long_shots', 'aggression', 'interceptions', 'positioning',
           'vision', 'penalties', 'marking', 'standing_tackle', 'sliding_tackle',
           'gk_diving', 'gk_handling', 'gk_kicking', 'gk_positioning',
           'gk_reflexes']
           
  Analyzing the dataset we can see that there are 3 catagorical features, 'preferred_foot', 'attacking_work_rate',           'defensive_work_rate'.
  Out of these 3 only preferred_foot is having proper data, but other two are messed up.
  
  So we decided to drop these two features along with 'id', 'player_fifa_api_id', 'player_api_id', 'date' featuress as these values seems not providing valueable info which will contribute in prediction.
  
  Also we checked the Columns for Backward elemination using OLS and found no feature is having P value > 0.05, so no need to drop any columns.
  
  Now, we need to perform LebelEncoding on preferred_foot column (as there are only two unique values in preferred_foot, no need to go for oneHotencoding).
  
  After this all make overall_rating as y and rest of features in X
  
  Now, fit this data in LinearRegressin and we can see the score is coming as 83.661%
  XGBoost gives the score as 93.577%
  DecisionTreeRegressor gives 96.614%
  And Finally we try with different n_estimator values for Random Forest Regression and get the score as 98.479%
  
  This is the best accuracy Score I can achive.

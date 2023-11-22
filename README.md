# NFL_Champion
![NFL_Champion_Art](https://github.com/allenjake440/NFL_Champion/assets/134075534/0a2fdb5d-5c47-483e-92e7-d93e49a9dcec)


[Medium Article](https://allenjake440.medium.com/predicting-the-nfl-champion-with-machine-learning-7c6eede5a4d2)


> First ever machine learning project (using phyton and excel), the goal with this project is create an effective model approach for the predicting NFL Champion (super-bowl winner), right before the playoffs start. 

### Project Procedure:

## Excel

•	1st: Gather player (offense and defensive) player data and gather team data (advanced, basic, defensive, and offensive team statistics). Data is all pro-football reference.com.

•	2nd: Feature engineering (re-created/made new features) create statistics that measure strength of the players on the teams as well as playoff experience of the team.

•	3rd: Create raw data set, check for nans, and send to juypterlab.


## Phyton

•	1st: Read in raw data file and raw data league rank file for data exploration. 

•	2nd: Preprocesses take out multi-correlated features and remove other useless features.

•	3rd: Identfiy the best model for our problem (Random Forest Regressor), hand-tune parameters (trees, splits, and depth). 

•	4th: Identify error metrics to evalute our model on all levels. This includes basic error metrics such as sse, mse, rmse, and computing a ranking error metric to identify champion and top 4 finishing precision (Average Precision).

•	5th: Export predictions and importance to power-bi to analyze results.

## Feature Exploration
![FeaCorr1](https://github.com/allenjake440/NFL_Champion/assets/134075534/8fb273cb-e295-4cdf-9fc9-167bab7d6da5)
![MultiCorrTable](https://github.com/allenjake440/NFL_Champion/assets/134075534/254f1ca2-c9df-4b4b-b88a-15076432968b)
![OffVDeff](https://github.com/allenjake440/NFL_Champion/assets/134075534/4c5340ec-2c90-47a1-a1f4-157b568b7896)
![mvpsharetoCS](https://github.com/allenjake440/NFL_Champion/assets/134075534/5f5c78df-3f89-4b8e-b2cc-d82768fb50f3)

## Results/Findings:
![ChampionTable](https://github.com/allenjake440/NFL_Champion/assets/134075534/4eb28339-b56e-43ad-b103-1d10651660c5)
![23SeaComp](https://github.com/allenjake440/NFL_Champion/assets/134075534/0d260b2b-14f5-41a9-9f78-d110111042b8)
![FeaImp](https://github.com/allenjake440/NFL_Champion/assets/134075534/556e226f-503b-44fa-95e7-a4cabb814e77)
![HeatTableFeaImp](https://github.com/allenjake440/NFL_Champion/assets/134075534/2a44086e-d57c-40d7-ae41-27b149192243)



# NFL_Champion
![linkin_art_nfl_trophy](https://github.com/allenjake440/NFL_Champion/assets/134075534/0657811b-27c3-4064-aef3-ea8c8de335ef)

[Medium Article](https://allenjake440.medium.com/predicting-the-nfl-champion-with-machine-learning-7c6eede5a4d2)


> Using Machine learning to predict the NFL Champion (super-bowl winner), right before the playoffs start. 

### Project Procedure:

## Excel

•	1st: Gather player (offense and defensive) player data and gather team data (advanced, basic, defensive, and offensive team statistics). Data is all pro-football reference.com.

•	2nd: Feature engineering (re-created/made new features) create statistics that measure strength of the players on the teams as well as playoff experience of the team.

•	3rd: Create raw data set, check for nans, and send to juypterlab.


## Python

•	1st: Read in raw data file and raw data league rank file for data exploration. 

•	2nd: Preprocesses take out multi-correlated features and remove other useless features.

•	3rd: Identfiy the best model for our problem (Random Forest Regressor), hand-tune parameters (trees, splits, and depth). 

•	4th: Identify error metrics to evalute our model on all levels. This includes basic error metrics such as sse, mse, rmse, and using average precision to measure champion and top 4 teams predictability. 

•	5th: Export

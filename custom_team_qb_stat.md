# Team Rating Custom – The Science Behind the Statistic

**Team Rating Custom** is a weight based formula, using critical team and player features to deliver a score that reflects a team's strength in a given season. More importantly, this metric is designed to predict post-season success, with scores scaled from 0 to 10.

## Methodology - Understanding whats important in the Formula.

1. **Weighted Scoring**: Each feature is multiplied by a defined weight (detailed below), determined through insights, trial and error.
2. **Average Team Feature Importance**: To assess feature significance for the average team within the team rating metric:
   - First, calculate the average value for each feature.
   - Next, multiply this average by the corresponding weight.
   - Finally, divide each weighted value by the sum of all weighted values to yield the relative importance of each feature.
3. **Pearson Correlation Coefficients**: Whats the PCC for each feature to the result of the metric.

The code and visualizations provided clarify each feature's weight (as a percentage) in calculating the Team Rating Custom metric. See the `nfl_champ_data` file for complete code details.

### Feature Explained:

| Feature                           | Description                                                                                       
|-----------------------------------|---------------------------------------------------------------------------------------------------
| `W`                               | Team's total regular season wins                                                                  
| `625_rec`                         | Team's regular season record ≥ 0.625                                                              
| `SRS_greater_than_1.5_pts`        | Adjusted margin of victory > 1.5 pts/game in regular season                                      
| `sum_mvp_shares`                  | Total MVP votes accumulated by all players                                                        
| `sum_dpoy_shares`                 | Total Defensive Player of the Year votes accumulated by all players                               
| `sum_cpoy_shares`                 | Total Comeback Player of the Year votes accumulated by all players                                
| `sum_opoy_shares`                 | Total Offensive Player of the Year votes accumulated by all players                               
| `sum_playoff_games`               | Total past playoff games played by each player                                                    
| `40_50+_perc_x_makes`               | The teams starting kickers regular season total 40-50 yard field goal percentage times the how many of those he has made 

### Bar Charts - Team Rating Custom

<div align="center">
  <img src="https://github.com/user-attachments/assets/64c45f52-c2af-4d9d-a3de-7ae0327c1545" alt="team_rat_cus">
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/64c45f52-c2af-4d9d-a3de-7ae0327c1545" alt="team_rat_cus">
</div>


### Code for Custom Rating Calculation

```python
all_team_advance_data['team_rating_custom'] = (
    (all_team_advance_data['40_50+_perc_x_makes'] * 0.006666666666664085) +
    (all_team_advance_data['sum_mvp_shares'] * 0.2166666666666664) +
    (all_team_advance_data['sum_franchise_L1S_cs'] * 0.3333333333333346) +
    (all_team_advance_data['sum_dpoy_shares'] * 0.15000000000000088) +
    (all_team_advance_data['sum_opoy_shares'] * 0.049999999999998594) +
    (all_team_advance_data['sum_cpoy_shares'] * 0.2666666666666677) +
    (all_team_advance_data['Scoring_FG%'] * 0.24999999999999487) +
    (all_team_advance_data['W'] * 0.18333333333333468) +
    (all_team_advance_data['625_rec'] * 2.3333333333333357) +
    (all_team_advance_data['SRS_greater_than_1.5_pts'] * 2.3333333333333357) + 
    (all_team_advance_data['sum_playoff_games'] * 0.00011666666666662269)
)
```

# Season QuarterBack Rating Custom – The Science Behind the Statistic

**Season QuaterBack Rating Custom (QBSR o QBSR_rk)** is a scaled regression-based formula, that returns a season quarterback score on a range form 5 - 20, for only the teams main starting quarterback for that specific season. This statistic encompasses factors like how many touchdowns did that QB deliver that season, how mvp votes have they add in the past x years, their playoff success in the last 5 seasons, their age, current season completion percentage, season sacks, season interception percentage, team season record, and the amount of long passes thrown that season. Yea... it's alot.

## Methodology

1. **Weighted Scoring**: Each feature is multiplied by a defined weight (detailed below), determined through insights, trial and error, and domain expertise.
2. **Feature Importance**: To assess feature significance within the quarterback season rating metric:
   - First, calculate the average value for each feature.
   - Next, multiply this average by the corresponding weight.
   - Finally, divide each weighted value by the sum of all weighted values to yield the relative importance of each feature.

The code and visualizations provided clarify each feature's weight (as a percentage) in calculating the QB Season Rating Custom metric. See the `nfl_champ_data` file for complete code details.

### Feature Weights Breakdown

| Feature                           | Description                                                                                       
|-----------------------------------|---------------------------------------------------------------------------------------------------|
| `W-L%`                               | Team's total regular season win percentage                                                              
| `TD`                         | How many touchdowns did the QB complete that regular season                                                          
| `sum_mvp_shares_L4S_cs`        | The QB's total past MVP votes over the last 4 seasons                                
| `sum_player_L5S_cs`                  | The QB's total past playoff wins in the last 5 seaosons                                                       
| `Sk`                 | How many times has the QB been sacked that regular season                             
| `sum_player_L1S_cs`                 | The QB's total past playoff wins last season                                 
| `QB_age`                 | How old is QB for that regular season                                 
| `Lng`                 | The QB's regular season total long passes thrown                              
| `Int%`                 | QB's regular season interception percentage                               
| `Cmp%`               | QB's regular season completion percentage                                                

### Code for Custom Rating Calculation

```python
top_players_passing_data['QB_sea_rating_custom'] = (
    (top_players_passing_data['sum_mvp_shares_L4S'] * 0.7605965360040652) +
    (top_players_passing_data['sum_player_L5S_cs'] * 0.11983696830206082) +
    (top_players_passing_data['sum_player_L1S_cs'] * 0.2493432963366484) +
    (top_players_passing_data['QB_Age'] * 0.0076112412316544946) +
    (top_players_passing_data['TD'] * 0.05494813431690466) +
    (top_players_passing_data['Cmp%'] * 0.14757574354200506) +
    (top_players_passing_data['Int%'] * -0.010742909524878155) +
    (top_players_passing_data['Sk'] * -0.0009641855158425538) + 
    (top_players_passing_data['Lng'] * 0.001811828880220935) +
    (top_players_passing_data['W-L%'] * 6.495133212900368) 
)
```

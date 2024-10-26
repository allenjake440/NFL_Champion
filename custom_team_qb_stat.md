# Team Rating Custom – The Science Behind the Statistic

**Team Rating Custom** is a scaled regression-based formula, leveraging critical team and player features to deliver a score that reflects a team's strength in a given season. More importantly, this metric is designed to predict post-season success, with scores scaled from 1 to 10.

## Methodology

1. **Feature Scaling**: Each feature is min-max scaled.
2. **Weighted Scoring**: Features are multiplied by specific weights (detailed below) based on insights, trial and error, and domain expertise.

The code and visualizations provided clarify each feature's weight (as a percentage) in calculating the Team Rating Custom metric. See the `nfl_champ_data` file for complete code details.

### Feature Weights Breakdown

| Feature                           | Description                                                                                       | Weight (%) |
|-----------------------------------|---------------------------------------------------------------------------------------------------|------------|
| `W`                               | Team's total regular season wins                                                                  | 28.33      |
| `625_rec`                         | Team's regular season record ≥ 0.625                                                              | 22.56      |
| `SRS_greater_than_1.5_pts`        | Adjusted margin of victory > 1.5 pts/game in regular season                                      | 22.56      |
| `sum_mvp_shares`                  | Total MVP votes accumulated by all players                                                        | 9.6        |
| `sum_dpoy_shares`                 | Total Defensive Player of the Year votes accumulated by all players                               | 4.54       |
| `sum_cpoy_shares`                 | Total Comeback Player of the Year votes accumulated by all players                                | 3.45       |
| `sum_opoy_shares`                 | Total Offensive Player of the Year votes accumulated by all players                               | 1.19       |
| `sum_playoff_games`               | Total past playoff games played by each player                                                    | 0.61       |

### Bar Chart Feature Weights Breakdown

<div align="center">
  <img src="https://github.com/user-attachments/assets/76efcff1-8068-45e5-a402-a3c281e798cf" alt="team_rat_cus">
</div>

### Code for Custom Rating Calculation

```python
all_team_advance_data['team_rating_custom'] = (
    ((all_team_advance_data['40_50+_perc_x_makes'] * 0.4799999999999958) +
    (all_team_advance_data['sum_mvp_shares'] * 2.9763500000000005) +
    (all_team_advance_data['sum_franchise_L1S_cs'] * 0.9999999999999937) +
    (all_team_advance_data['sum_dpoy_shares'] * 1.4129999999999925) +
    (all_team_advance_data['sum_opoy_shares'] * 0.3710999999999902) +
    (all_team_advance_data['sum_cpoy_shares'] * 1.0720000000000038) +
    (all_team_advance_data['Scoring_FG%'] * 0.7499999999999942) +
    (all_team_advance_data['W'] * 8.799999999999978) +
    (all_team_advance_data['625_rec'] * 7) +
    (all_team_advance_data['SRS_greater_than_1.5_pts'] * 7) + 
    (all_team_advance_data['sum_playoff_games'] * 0.18654999999999305)) / 3
)
```

# Season QuarterBack Rating Custom – The Science Behind the Statistic

**Season QuaterBack Rating Custom (QBSR o QBSR_rk)** is a scaled regression-based formula, that returns a season quarterback score on a range form 5 - 20, for only the teams main starting quarterback for that specific season. This statistic encompasses factors like how many touchdowns did that QB deliver that season, how mvp votes have they add in the past x years, their playoff success in the last 5 seasons, their age, current season completion percentage, season sacks, season interception percentage, team season record, and the amount of long passes thrown that season. Yea... it's alot.

## Methodology

1. **Feature Scaling**: Each feature is absoluated min-max scaled.
2. **Weighted Scoring**: Features are multiplied by specific weights (detailed below) based on insights, trial and error, and domain expertise.

The code and visualizations provided clarify each feature's weight (as a percentage) in calculating the QB Season Rating Custom metric. See the `nfl_champ_data` file for complete code details.

### Feature Weights Breakdown

| Feature                           | Description                                                                                       | Weight (%) |
|-----------------------------------|---------------------------------------------------------------------------------------------------|------------|
| `W-L%`                               | Team's total regular season win percentage                                                              | 50.15      |
| `TD`                         | How many touchdowns did the QB complete that regular season                                                          | 23.15      |
| `sum_mvp_shares_L4S_cs`        | The QB's total past MVP votes over the last 4 seasons                                | 12.62      |
| `sum_player_L5S_cs`                  | The QB's total past playoff wins in the last 5 seaosons                                                       | 3.86        |
| `Sk`                 | How many times has the QB been sacked that regular season                             | 3.09       |
| `sum_player_L1S_cs`                 | The QB's total past playoff wins last season                                 | 1.93       |
| `QB_age`                 | How old is QB for that regular season                                 | 1.54       |
| `Lng`                 | The QB's regular season total long passes thrown                              | 1.35       |
| `Int%`                 | QB's regular season interception percentage                               | 1.16       |
| `Cmp%`               | QB's regular season completion percentage                                                | 1.16       |

### Bar Chart Feature Weights Breakdown

<div align="center">
  <img src="https://github.com/user-attachments/assets/5ea668b8-2cd3-4e27-90ce-be5266ee6618" alt="qb_rat_cus">
</div>

### Code for Custom Rating Calculation

```python
top_players_passing_data['QB_sea_rating_custom'] = (
    (top_players_passing_data['sum_mvp_shares_L4S'] * 1.635) +
    (top_players_passing_data['sum_player_L5S_cs'] * .5) +
    (top_players_passing_data['sum_player_L1S_cs'] * .25) +
    (top_players_passing_data['QB_Age'] * .2) +
    (top_players_passing_data['TD'] * 3) +
    (top_players_passing_data['Cmp%'] * .15) +
    (top_players_passing_data['Int%'] * -.15) +
    (top_players_passing_data['Sk'] * -.4) + 
    (top_players_passing_data['Lng'] * .175) +
    (top_players_passing_data['W-L%'] * 6.5) 
)
```

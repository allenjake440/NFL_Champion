# Predicting the NFL Champion Using Machine Learning

<div align="center">
  <img src="https://github.com/user-attachments/assets/b45d2a51-6f4f-46f2-a793-ce2287a69bd3" alt="linkin_art_nfl_trophy">
</div>

## Overview

Using machine learning to predict the NFL Champion for upcoming years based on historical data.

### [Read the Medium Article](https://allenjake440.medium.com/predicting-the-nfl-champion-with-machine-learning-7c6eede5a4d2)

---

## Data Sources (Since 1990)

- [Pro Football Reference](https://www.pro-football-reference.com/)

---

## Project Details

This project builds on my NBA champion prediction project, but much of the data for this NFL project was collected manually over time. 

The project uses machine learning techniques in Python to predict future NFL champions.

### How to Set Up and Run the Project

1. For predicting future seasons (e.g., 2025, 2026), you will need to manually copy the new season data from the websites linked below.
2. Format the data appropriately (using Excel, Python, or other tools) according to the required structure.
3. Run the Python file `nfl_champ_data.py` to load the data.
4. Then run `nfl_champ_ml.py` to generate predictions.

---

## CSV Files and Data Sources

Here’s a list of the required CSV files and their corresponding sources:

- **all_coaches_data**: [Pro Football Reference - Coaches Data](https://www.pro-football-reference.com/years/2023/coaches.htm)
- **all_player_award_data**: [Pro Football Reference - Player Awards](https://www.pro-football-reference.com/awards/awards_2023.htm)
- **all_player_defense_data**: [Pro Football Reference - Defensive Stats](https://www.pro-football-reference.com/years/2023/defense.htm)
- **all_player_kicking_data**: [Pro Football Reference - Kicking Stats](https://www.pro-football-reference.com/years/2023/kicking.htm)
- **all_player_passing_data**: [Pro Football Reference - Passing Stats](https://www.pro-football-reference.com/years/2023/passing.htm)
- **all_player_receiving_data**: [Pro Football Reference - Receiving Stats](https://www.pro-football-reference.com/years/2023/receiving.htm)
- **all_player_rushing_data**: [Pro Football Reference - Rushing Stats](https://www.pro-football-reference.com/years/2023/rushing.htm)
- **all_team_advance_data**: [Pro Football Reference - Advanced Team Stats](https://www.pro-football-reference.com/years/2023/index.htm)
- **all_team_defense_data**: [Pro Football Reference - Defensive Team Stats](https://www.pro-football-reference.com/years/2023/opp.htm)
- **all_team_games_data**: [Pro Football Reference - Team Game Results](https://www.pro-football-reference.com/years/2023/games.htm)
- **all_team_index_custom**: Update this file for any future team changes.
- **all_team_offense_data**: [Pro Football Reference - Offensive Team Stats](https://www.pro-football-reference.com/years/2023/)
- **all_team_passing_offense_data**: [Pro Football Reference - Passing Offense Stats](https://www.pro-football-reference.com/years/2023/)
- **all_team_pso_data**: [Pro Football Reference - Preseason Odds](https://www.pro-football-reference.com/years/2023/preseason_odds.htm)

---

## Notes

- This project was built using hand-collected data. For future seasons, the data should be manually updated and formatted appropriately.
- The project involves machine learning techniques using Python to predict NFL champions based on various statistical sources.

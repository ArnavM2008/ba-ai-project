# Brazilian Cup Matches, ba-ai-project

Kaggle Link: https://www.kaggle.com/datasets/ricardomattos05/jogos-do-campeonato-brasileiro

Week 1: Python + AI

Row Representation: Each row represents one match in the Brazilian Cup, showing records of the round, date & time, the home and away team, the goals scored by each team, and the season.

Summary: During our Business Analytics and AI career plan meeting, I learned how to use Python and AI in data work. I used Python to clean repositories by finding and fixing errors in data. This showed me the importance of cleaning data before doing any sort of analysis. After cleaning the data I then built a bar graph based on the information provided.

Diagnostic Question: What factors make the home advantage in the Brazilian Cup stronger or weaker across seasons or rounds, and why?

Week 2: SQL Warm-up

Number measured: home_goal & away_goal

Group: season

Rewritten Question: How does the difference between home and away goals vary from season to season in the Brazilian Cup?

## SQL
  
**Q1 - How many matches did the home team win?**


```sql
SELECT COUNT(*) AS home_wins
FROM data
WHERE home_goal > away_goal
```


Finding: The home team won 579 matches.

**Q2 - Which season had the greatest average difference between home goals and away goals?**


```sql
SELECT season, AVG(home_goal - away_goal) AS avg_goal_difference
FROM data
GROUP BY season
ORDER BY avg_goal_difference DESC
```


Finding: The 2014 season had the greatest average home away goal difference with and average difference of .497 goals per match.


**Q3 - What are the top 5 home teams that had the highest total goals difference between home and away goals in 2020?
**

```sql
SELECT home_team, SUM(home_goal - away_goal) AS total_goal_difference
FROM data
WHERE season = 2020
GROUP BY home_team
ORDER BY total_goal_difference DESC
LIMIT 5
```

Finding: During season 2020, Palmeiras - SP had the highest total home to away goal difference of 6, followed by Fluminense - RJ, Ferroviária, and Ceará with differences of 6 goals each, and Brusque with 4.

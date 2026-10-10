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

    ##SQL
  
**Q1 - How many matches had 4 or more goals?**


```sql
SELECT COUNT(*) AS orders
FROM data

WHERE home_goal + away_goal >= 4 
```


Finding: 278 matches had 4 or more total goals.

**Q2 - Which season had the most ties in matches?**


```sql
SELECT season, COUNT(*) AS ties
FROM data
WHERE home_goal = away_goal


GROUP BY season
ORDER BY ties DESC
LIMIT 1
```


Finding: The 2016 season had the most ties, with 50 ties.


**Q3 - What are the top 5 home teams that had the highest total goals in a specific season?
**

```sql
SELECT home_team, SUM(home_goal) AS total_goals
FROM data
WHERE season = 2020


GROUP BY home_team
ORDER BY total_goals DESC
LIMIT 5
```

Finding: During season 2020, the top 5 home teams scoring the most goals were Ceará, Ferroviária, Brusque, Palmeiras, and Atlético.

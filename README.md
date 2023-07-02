![2022 FIFA World Cup](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/2022_FIFA_World_Cup.svg.png)
# Soccer World Cup Prediction
## Introduction
### Context:
Children First Soccer (CFS) Ltd. (non-profit that financially supports underprivileged children to enter into the professional world of soccer) wants to promote soccer in the developing markets across Asia (e.g. Laos, Cambodia, Myanmar etc.) leading up to the 2026 FIFA World Cup in USA, Canada and Mexico. CFS would like to understand which competitive teams should drive promotional campaigns within these markets in order to create excitement and passion for the game. CFS believes this will set up the foundation for children (both boys & girls), specifically in the age group of 6-15, to be coached, trained and presumably selected for the 2027 FIFA U-17 Boys World Cup in China & Girls World Cup in New Zealand respectively.<br>

### Criteria for Success:
CFS needs to understand the countries who have a likelihood to qualify into the Round of 16, Quarter Finals, Semi Finals and Finals specifically for the 2022 FIFA World Cup in Qatar in order to drive a 5 year strategy in the developing Asia markets leading up to the U-17 World Cups in 2027. The 5 year roadmap is segmented into 2 Phases:

**Phase 1:**  Focused on creating excitement in the markets and;<br>
**Phase 2:** Drive training programs across priority markets/ age groups. 

This proposal is focused on *Phase 1* only.

### Scope of Solution:
Prediction will be based only on teams who have participated in FIFA Soccer World Cups till date and their performance in international matches.
Constraints:

Factors such as venue, host country weather, timing of the tournament, referee judgment, Video Assistant Referee (VAR) interventions, squad formation, in-game tactical switches, and player concentration and stamina all play a huge role in predicting the final outcome. These elements are relatively new to sports science and unsure about how to apply them as influential statistical factors in an algorithm.

### Stakeholders:
CFS CMO (Chief Marketing Officer)<br>
CFS COO (Chief Operating Officer)<br>
CFS APAC Regional Head<br>
Ministry of Sports (APAC Developing Markets)<br>

### Key data Sources:

1. World Cups
2. 2022 World Cup Groups
3. 2022 World Cup Matches
4. World Cup Matches Stats
5. International Matches Stats
6. FIFA World Cup Ranking
7. FIFA International Matches

## Data
### Data Files:
All of the data utilized for this project is online user-entered and prone to discrepancies which made it a particularly challenging dataset to clean. The dataset contains 7 tables in CSV format:

1. The [World Cups](https://www.kaggle.com/code/thedevastator/soccer-world-cup-2022-prediction/input?select=world_cups.csv) table outlines each World Cup in history, including the year, host country, and winner
2. The [2022 World Cup Groups](https://www.kaggle.com/code/thedevastator/soccer-world-cup-2022-prediction/input?select=2022_world_cup_groups.csv) table includes all the qualified countries for this year's World Cup, the group they were drawn to, and their FIFA Ranking
3. The [2022 World Cup Matches](https://www.kaggle.com/code/thedevastator/soccer-world-cup-2022-prediction/input?select=2022_world_cup_matches.csv) table contains the date and opponents for each of the 64 matches scheduled for the 2022 FIFA World Cup
4. The [World Cup Matches](https://www.kaggle.com/code/thedevastator/soccer-world-cup-2022-prediction/input?select=world_cup_matches.csv) table contains all the results from the previous editions of the World Cup
5. The [International Matches](https://www.kaggle.com/code/thedevastator/soccer-world-cup-2022-prediction/input?select=international_matches.csv) table contains all the results from every international match in history outside of the World Cup for each qualified country
6. The [FIFA World Cup Ranking](https://www.kaggle.com/datasets/cashncarry/fifaworldranking?select=fifa_ranking-2022-12-22.csv) table contains ranking of all countries from 1992 to 2022
7. The [FIFAallMatchBoxData](https://www.kaggle.com/datasets/kaito510/fifa-world-cup-match-stats?select=FIFAallMatchBoxData.csv) contains information of international matches played between 2012 to 2017 with data on home & away team goals, shots on target, possession percentage etc.

In order to properly clean these tables, I needed to delete specific extraneous information that would not serve the analysis.

## About the 2022 FIFA World Cup
Here's some context you may need into how the tournament plays out.<br>

![Group Stages](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/2022%20FIFA%20Soccer%20World%20Cup%20Group%20Stages.webp)

The 32 qualified countries are drawn into 8 groups with 4 teams each. For the initial group stage, each country plays the others in their group once (3 matches) and gets 3 points for a win, 1 for a draw, and 0 for a loss. Once the group stage ends, the two countries with the most points from each group advance to the round of 16.<br>

![Knockout Bracket](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/2022%20World%20Cup%20Knockout%20Bracket.png)

The bracket for the round of 16, and subsequent stages, is determined by splitting up the winner from each group and facing them off against the runner-up from another group.<br>

The team that wins each match advances to the next round until a winner is crowned!<br>

## Data Wrangling
All 7 datasets in scope were cleaned.<br>

The data types across all 7 tables were consistent; however the *“Win Condition”* column in both World Cup Matches and International Matches tables had to be dropped due to null values and this was also considered to be a low priority feature to be analyzed.<br>

The *“Winning Team”* & *“Losing Team”* columns are expected to have null values when the match is a draw.<br>

## Exploratory Data Analysis
Analysis was focused on match results, player statistics, and overall team performance utilizing data from international matches played from 2012 to 2017. This was done utilizing the FIFAallMatchBoxData  table. Data visualization techniques were utilized to explore patterns and trends in the data, and statistical methods to analyze and make inferences about the dataset.<br>

### Possession Comparison:
![Possession](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Possession%20%25.png)<br>
On average, team1 has a better possession % than team2.<br>

### Possession versus Goals scored:
![Possession Team1](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Team%201%20Possession%20vs%20Goals.png)<br>
![Possession Team2](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Team%202%20Possession%20vs%20Goals.png)<br>
Both team1 and team2 scored more goals when they had more ball possession with team1 scoring more than team2.<br>

### Comparison of Total Attempts, On Target Attempts, and Goals scored:
![Attempts Goals](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Attempts%20%26%20Goals.png)<br>
Team1 had better stats across Total Attempts, On Target Attempts as well as Goals Scored compared to team2.<br>

### Distribution of Goals:
![Team1 Distribution](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Team%201%20Goals.png)<br>
![Team1 Distribution](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/EDA%20-%20Team%202%20Goals.png)<br>
Team2 had a better distribution of goals scored compared to team1.<br>

**CONCLUSION:** It can be inferred that possession and attempts are crucial factors in determining the number of goals scored in a match, however, it is not the only factor, other factors like team strategies, player skills, and luck also play a role.<br>

## Featured Engineering & ML
The objective was to prepare the data to apply feature engineering methods that will create the database in order to build Machine Learning algorithms to predict the winner of the 2022 Soccer World Cup.<br>

### Create Features:
The datasets were filtered to only utilize data from 2018 leading up to the  2022 World Cup to make it relevant. The idea here is to create possible features that have an impact on predicting football games. By intuition, we say that features that impact could be:<br>
1. Past game points made
2. Past goals scored and suffered
3. The importance of game (friendly or not)
4. Rank of the teams
5. Rank increment of the teams
6. Goals made and suffered by ranking faced<br>

So, the first thing to do is create a feature that says which team won and how many points they made in the game. The game points were assigned as 3 for win, 1 for draw and 0 for lose and which are different from the FIFA rank points that are already in the database. Also, it's supposed that FIFA Rank points and FIFA Ranking of the same team are negatively correlated, and we should use only one of them to create new features. This supposition is checked below:
![HeatMap](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20HeatMap.png)<br>
### Feature Analysis:
![BoxPlot1](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20BoxPlot1.png)<br>
![BoxPlot2](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20BoxPlot2.png)<br>
Based on the boxplots, *“rank difference”* and *“is_friendly”* are the only good separators of data. But, we can create new features that differentiates between home and away teams and analyze if they are good at separating the data.<br>

![BoxPlot3](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20BoxPlot3.png)<br>
With that plot, we see that *“goal differences”* (full and last 5 games) and *“goals suffered”* (full and last 5 games) are good separators.<br>

Now, we have 6 features:<br>
1. rank_dif
2. goals_dif
3. goals_dif_l5
4. goals_suf_dif
5. goals_suf_dif_l5
6. is_friendly<br>

We can create other features, like differences of points made, differences of points made by rank faced and differences of rank faced.<br>
![BoxPlot4](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20BoxPlot4.png)<br>
*“Difference of points”* (full and last 5 games), *“difference of points by ranking faced”* (full and last 5 games) and *“difference of rank faced”* (full and last 5 games) are good features.<br> 

Some of the generated features have very similar distributions which were analyzed using the following scatterplots:<br>
![Splot1](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20SP1.png)<br>
![Splot2](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20SP2.png)<br>
![Splot3](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20SP3.png)<br>
![Splot4](https://github.com/ancyjperumbilly/Soccer-World-Cup-Prediction/blob/main/5.%20Reference%20Images/FE%20-%20SP4.png)<br>
*“Goals difference by ranking faced”* and its last 5 games version has very similar distributions. So, we will use only the full version (goals_per_ranking_dif). For *“differences of rank faced”*, *“game points by rank faced”* and *“mean game points by rank faced”*, the two versions (full and 5 games) are not so similar. So, we will use both.<br>

Final features that were selected were:

1. rank_dif
2. goals_dif
3. goals_dif_l5
4. goals_suf_dif
5. goals_suf_dif_l5
6. dif_rank_agst
7. dif_rank_agst_l5
8. goals_per_ranking_dif
9. dif_points_rank
10. dif_points_rank_l5
11. is_friendly

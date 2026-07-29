Conducted an end-to-end SQL analysis on the IPL 2025 Batters dataset to derive meaningful insights into player and team performances. Imported the dataset into a relational database and executed a wide range of SQL queries using filtering, sorting, aggregation, and grouping techniques to answer business-oriented questions.
# Questions for Indian Premier League  Analysis 
Use Cricket;
select * from ipl;
select * from ipl order by player_name asc;
# Addregate questions 
#Find the total runs scored by all players.
select sum(runs) as total_run from ipl;

#Find the total number of sixes hit by all players.
describe ipl;
select sum(6s) as total_six from ipl;

#Find the total number of fours hit by all players.
select sum(4s) as total_fours from ipl;

#Find the total runs scored by each team.
select * from ipl;
select team , sum(runs)  from ipl group by team order by sum(runs) desc ;

#Find the total sixes hit by each team.
select team , sum(6s)as total_sixes from ipl group by team order by sum(6s) desc;

#Find the total fours hit by each team.
select team , sum(4s)as total_fours from ipl group by team order by sum(4s) desc;

#Find the total centuries (100s) scored by each team.
select team , sum(100s)as total_Centuries from ipl group by team order by sum(100s) desc;

#Find the total half-centuries (50s) scored by each team.
select team , sum(50s)as half_centuries from ipl group by team order by sum(50s) desc;

#Find the average batting average of all players.
select*from ipl;
select avg(AVG) from ipl;
SELECT ROUND(AVG(AVG), 2) AS average_batting_average FROM ipl; # used round () for roundoff the decimal 

#Find the average strike rate of all players
select round(avg(SR),2) as avg_strike_rate from ipl;

#Find the average runs scored by players in each team.
select* from ipl;
select team , round(avg(runs),2) as avg_runs from ipl group by team order by avg_runs desc;

#Find the average strike rate for each team.
select team , round(avg(SR),2) as avg_strike_rate from ipl group by team order by avg_strike_rate desc ;

#Find the average batting average for each team.
select team, round(avg(AVG),2)as avg_batting from ipl group by team order by avg_batting desc;

#Find the average number of sixes hit by players in each team.
select team, round(avg(6s),2) as sixes from ipl group by team order by sixes desc;

#Find the player with the minimum number of runs.
select * from ipl;
select player_name , min(runs) from ipl where runs=(select min(runs) from ipl)  group by player_name order by min(runs) asc;

#Find the minimum strike rate.
select min(SR) from ipl;

#Find the minimum batting average.
select min(AVG) from ipl;

#Find the team with the minimum total runs.
select team , min(runs) as total_run from ipl group by team order by total_run;

#Find the player with the highest number of runs.
select * from ipl;
 select player_name , max(runs) as max_runs from ipl group by player_name order by max_runs desc;
 
 #Find the highest strike rate.
 select max(SR) as Strike_rate from ipl;
 
 #Find the highest batting average.
 select max(AVG) as batting_avg from ipl;
 
 #Find the player with the maximum number of sixes.
 select player_name , max(6s) as Sixes from ipl group by player_name order by Sixes desc;
 
 #Find the player with the maximum number of fours.
 select player_name , max(4s) as Fours from ipl group by player_name order by Fours desc;
 
 #Find the team with the highest total runs.
 select team , max(runs)as Runs from ipl group by team order by Runs desc ;
 
 #Display teams whose total runs are greater than 1000.
 select team from ipl where runs > 400;
 select *from ipl;
 
 #Display teams whose total sixes are greater than 80.
 select team from ipl where 6s > 20;
 
 #Display teams having more than 3 players.
 select team , count(*)as total_players from ipl group by team having total_players >3;
 
 #Display teams whose average strike rate is greater than 140.
 select * from ipl;
 select team,round(avg(sr),0)as SR from ipl group by team having SR> 140 order by SR desc;
 
 #Display teams whose average batting average is greater than 40.
 select team , round(avg(AVG),0) as Batting_avg from ipl group by team having Batting_avg>40 order by Batting_avg desc; # none of the team is greater that batting avg 40 
select team , round(avg(AVG),2) from ipl group by team ;

#Display teams whose total fours are greater than 100.
select team , sum(4s) as Fours from ipl group by team having Fours >100 order by Fours desc;

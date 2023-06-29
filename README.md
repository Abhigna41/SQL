# SQL
This is a 2008-2020 IPL dataset. Analysing this dataset using SQL in postgresql.
select * from deliveries
select * from IPL

select * from ipl


select * from ipl
where team1='Sunrisers Hyderabad' or team2='Sunrisers Hyderabad'
order by season ASC
   
   
select  count(team1) from ipl
Where team1='Sunrisers Hyderabad'

select team1,team2,winner from ipl
where team1='Sunrisers Hyderabad' OR team2='Sunrisers Hyderabad'
AND winner='Sunrisers Hyderabad'

select team1,team2,winner from ipl
where  team1='Sunrisers Hyderabad' OR team2='Sunrisers Hyderabad' AND winner!='Sunrisers Hyderabad'



select count(*) from ipl
where winner!='Sunrisers Hyderabad' And City='Hyderabad'


select count(*) from ipl
where winner='Sunrisers Hyderabad' And City='Hyderabad'


select* from ipl
order by date

select* from ipl
where team1='Sunrisers Hyderabad' or team2='Sunrisers Hyderabad' AND winner<>'Sunrisers Hyderabad'
order by date

select * from ipl
where date='16-05-2009'

select * from ipl
where result='tie'
order by season
ASC

select batting_team, count(*) from deliveries
group by batting_team
order by count
ASC

select count(*) from deliveries

select * from deliveries

select * from deliveries 
where player_dismissed='DA Warner' and over<=5

select count(*) from deliveries 
where player_dismissed='DA Warner' and over<=5

select * from deliveries 
where player_dismissed='DA Warner' 


select   dismissal_kind, count(dismissal_kind) from deliveries 
where player_dismissed='DA Warner' 
group by dismissal_kind
order by count 
ASC


select bowler, sum(extra_runs) as extras from deliveries
where extra_runs>= 5
group by bowler 
order by extras

select bowling_team from deliveries

select bowler, sum(extra_runs) as extras from deliveries
where extra_runs>= 5 And bowling_team='Sunrisers Hyderabad'
group by bowler 
order by extras


select * from deliveries
Inner Join ipl
on deliveries.match_id=ipl.id



select * from ipl
Inner Join deliveries
on ipl.id=deliveries.match_id

select * from ipl
Full Outer Join deliveries
on ipl.id=deliveries.match_id


select * from ipl
Left outer Join deliveries
on ipl.id=deliveries.match_id
where deliveries.bowling_team='Sunrisers Hyderabad'


select * from ipl

select distinct team1 from ipl

select * from ipl limit 3;

select * from ipl
where team1 LIKE 'S%'

SELECT winner, COUNT(winner) AS count
FROM ipl
GROUP BY winner
HAVING COUNT(*) > 1;


SELECT winner, COUNT(winner) AS count
FROM ipl
GROUP BY winner
HAVING COUNT(winner) > 70;
order BY count(winner)


SELECT winner, COUNT(winner) AS count
FROM ipl
GROUP BY winner
HAVING COUNT(winner) > 70
ORDER BY COUNT(winner) DESC;


select max(win_by_runs) from ipl

select avg(win_by_runs) from ipl
SELECT *
FROM ipl
WHERE win_by_wickets IS NULL;

SELECT *
FROM ipl
WHERE win_by_wickets='5';

select count(wide_runs) from deliveries
where batting_team='Sunrisers Hyderabad' OR bowling_team='Sunrisers Hyderabad'

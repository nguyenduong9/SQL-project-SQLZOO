# SQL-project-SQLZOO
Nobel database
*/ 
Change the query shown so that it displays Nobel prizes for 1950.

SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
 
 * Show who won the 1962 prize for Literature.
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
Show the year and subject that won 'Albert Einstein' his prize.

select yr, subject
from Nobel
where winner like '%Einstein'
Show all details (yr, subject, winner) of the Literature prize winners for 1980 to 1989 inclusive.

select yr, subject, winner
from Nobel
where subject = 'Literature'
and yr >=1980 and yr<=1989

6.
Show all details of the presidential winners:
Theodore Roosevelt
Woodrow Wilson
Jimmy Carter
Barack Obama
SELECT * FROM nobel

  where winner IN ('Barack Obama',
                  'Theodore Roosevelt',
                  'Jimmy Carter', 'Woodrow Wilson')
                  

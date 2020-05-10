# SQL-project-SQLZOO
Nobel database
/* Change the query shown so that it displays Nobel prizes for 1950.
*/ 
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
 
 Show who won the 1962 prize for Literature.
 */ 
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'

--5. 
Show the year and subject that won 'Albert Einstein' his prize.
*/ 
select yr, subject
from Nobel
where winner like '%Einstein'

Show all details (yr, subject, winner) of the Literature prize winners for 1980 to 1989 inclusive.
*/
select yr, subject, winner
from Nobel
where subject = 'Literature'
and yr >=1980 and yr<=1989

*/ 6.Show all details of the presidential winners:
Theodore Roosevelt
Woodrow Wilson
Jimmy Carter
Barack Obama
SELECT * FROM nobel

  where winner IN ('Barack Obama',
                  'Theodore Roosevelt',
                  'Jimmy Carter', 'Woodrow Wilson')
                  
Show the winners with first name John
*/
select winner from nobel
where winner like 'John%'

Show the year, subject, and name of Physics winners for 1980 together with the Chemistry winners for 1984.
*/
select yr, subject, winner
from Nobel
where (subject = 'Physics' and yr = '1980' ) or (subject ='Chemistry' and yr = '1984')

Show the year, subject, and name of winners for 1980 excluding Chemistry and Medicine
*/
select yr, subject, winner 
from Nobel
where yr = '1980' and subject not in ('Chemistry', 'Medicine') 

10.Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)

*/ 
select yr, subject, winner
from Nobel 
where (subject = 'Medicine'and yr <1910) or (subject = 'Literature' and yr >=2004)

Find all details of the prize won by PETER GRÜNBERG
*/ 
select * 
from nobel
where winner like 'peter gr%nberg'

Find all details of the prize won by EUGENE O'NEILL
*/
select * 
from nobel
where winner like 'Eugene O%NEILL'

13.
Knights in order/ List the winners, year and subject where the winner starts with Sir. Show the the most recent first, then by name order.
*/
select * 
from nobel
where winner name like 'sir.%'
order by yr desc, winner

Show the 1984 winners and subject ordered by subject and winner name; but list Chemistry and Physics last.
*/ 
select winner, subject
from nobel
where yr = '1984'
ORDER BY 
CASE WHEN subject IN ('Physics','Chemistry') THEN 1 ELSE 0 END, 
  subject, 
  winner

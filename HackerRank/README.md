-  01. https://www.hackerrank.com/challenges/weather-observation-station-4/problem \
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table. \
Select (SELECT COUNT(city) FROM station) - (SELECT COUNT(DISTINCT city) FROM station) 

-  02. https://www.hackerrank.com/challenges/weather-observation-station-5/problem \
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. \
SELECT city, length(city) FROM station
WHERE LENGTH(city) = ( SELECT MIN(LENGTH(city)) FROM station )
ORDER BY city LIMIT 1;
SELECT city, length(city)  FROM station
WHERE LENGTH(city) = ( SELECT MAX(LENGTH(city)) FROM station )
ORDER BY city LIMIT 1; \

- 03. https://www.hackerrank.com/challenges/weather-observation-station-7/problem \
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates. \
SELECT Distinct City from Station Where city like "%a" OR city like "%e" OR city like "%i" OR city like "%o" OR city like "%u" 

- 04. https://www.hackerrank.com/challenges/weather-observation-station-8/problem \
  Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates. \
  SELECT DISTINCT city FROM station WHERE SUBSTRING(city, 1,1) IN ('a', 'e', 'i', 'o', 'u') AND SUBSTRING(city, length(city), 1) IN ('a', 'e', 'i', 'o', 'u');

- 05. https://www.hackerrank.com/challenges/more-than-75-marks \
  Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID. \
  Select name from Students where marks > 75 order by Substring(name,length(name)-2,3), id

- 06. https://www.hackerrank.com/challenges/binary-search-tree-1/problem \
SELECT
CASE
    WHEN p is null THEN concat(n,' Root')
    WHEN n in (SELECT p from BST) THEN concat(n, ' Inner')
    ELSE concat(n,'  Leaf')
END
from BST
ORDER BY n;

- 07. https://www.hackerrank.com/challenges/the-pads/problem \
SELECT 
CASE 
WHEN Occupation = 'Doctor' THEN concat(name,'(D)')
WHEN Occupation = 'Actor' THEN concat(name,'(A)')
WHEN Occupation = 'Singer' THEN concat(name,'(S)')
ELSE concat(name,'(P)')
END
FROM OCCUPATIONS
ORDER BY name;
SELECT concat('There are a total of ' , (SELECT count(*) FROM occupations WHERE occupation = 'Doctor'), ' doctors.');
SELECT concat('There are a total of ' , (SELECT count(*) FROM occupations WHERE occupation = 'Actor'), ' actors.');
SELECT concat('There are a total of ' , (SELECT count(*) FROM occupations WHERE occupation = 'Singer'), ' singers.');
SELECT concat('There are a total of ' , (SELECT count(*) FROM occupations WHERE occupation = 'Professor'), ' professors.');

- 08. https://www.hackerrank.com/challenges/the-report/problem
Select concat(name, ' ', grade, ' ', marks)
FROM Students as s 
INNER JOIN Grades AS g ON (
    ((s.marks DIV 10) * 10 = g.min_mark) OR 
    (s.marks = g.max_mark)
)
WHERE grade >= 8
order by grade desc, name;
Select concat('NULL ', grade, ' ', marks)
FROM Students as s INNER JOIN Grades as g on ((s.marks div 10) * 10) = g.min_mark
WHERE grade < 8
order by grade desc, marks

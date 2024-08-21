-  01. https://www.hackerrank.com/challenges/weather-observation-station-4/problem
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
Select (SELECT COUNT(city) FROM station) - (SELECT COUNT(DISTINCT city) FROM station) 

-  02. https://www.hackerrank.com/challenges/weather-observation-station-5/problem
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
SELECT city, length(city) FROM station
WHERE LENGTH(city) = ( SELECT MIN(LENGTH(city)) FROM station )
ORDER BY city LIMIT 1;
SELECT city, length(city)  FROM station
WHERE LENGTH(city) = ( SELECT MAX(LENGTH(city)) FROM station )
ORDER BY city LIMIT 1;

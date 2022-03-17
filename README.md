# Celebal_Week4_Assignment
[1] Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both 
have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

ANS:
SELECT NAME FROM STUDENTS
WHERE MARKS > 75 ORDER BY RIGHT(NAME, 3) ASC, ID;

[2] 
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

ANS:
SELECT CITY FROM STATION
WHERE CITY REGEXP '^[AEIOU]' ;

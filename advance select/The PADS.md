**Generate the following two result sets:**

**Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).**
**Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:**

![image](https://user-images.githubusercontent.com/90106232/190962358-d8f90736-5297-4e5c-bb95-c25abf6e9acf.png)

**where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.**

**Note: There will be at least two entries in the table for each type of occupation.**
**Input Format**
**The OCCUPATIONS table is described as follows:**
![image](https://user-images.githubusercontent.com/90106232/190962489-48ee278d-4eb7-4d71-9c0b-7d03dcf0b00c.png)
 
**Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.**
**Sample Input**

**An OCCUPATIONS table that contains the following records:**

![image](https://user-images.githubusercontent.com/90106232/190962593-ce6df2d4-37f6-4403-94bf-9ff3f11e2366.png)

# Solution 

```sql
(select  case when 
occupation = 'Doctor' then concat(name,'(D)')
when occupation = 'Professor' then concat(name, '(P)')
when occupation = 'Singer' then concat(name , '(S)')
when occupation = 'Actor' then concat(name, '(A)') end as df  
from occupations )
 
union
(select concat('There are a total of',' ',count(case when occupation = 'Doctor' then 'Doctor' end),' ','doctors.') from occupations)
union
(select 
concat('There are a total of',' ' ,count(case when occupation = 'Singer' then 'Singer' end),' ','singers.') from occupations) union
( select concat('There are a total of',' ', count(case when occupation = 'Actor' then 'Actor' end),' ','actors.') from occupations) union
(select concat('There are a total of',' ' ,count(case when occupation = 'Professor' then 'Professor' end),' ','professors.')
from occupations)
order by df
```

![image](https://user-images.githubusercontent.com/90106232/190962782-8c29c71a-f0e5-4962-ba3c-c439094ac7d5.png)


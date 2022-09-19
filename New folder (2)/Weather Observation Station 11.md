Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
![image](https://user-images.githubusercontent.com/90106232/190918035-fde684ae-9f1d-4018-aeb0-186ea47ace9d.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

# solution 
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE LOWER(SUBSTR(CITY,1,1)) NOT IN ('a','e','i','o','u') 
OR 
LOWER(SUBSTR(CITY, 
LENGTH(CITY),1)) NOT IN ('a','e','i','o','u');  
```

![image](https://user-images.githubusercontent.com/90106232/190918141-9619a1f1-8a01-471e-869a-9dd062f11872.png)

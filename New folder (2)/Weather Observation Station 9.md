## Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

**Input Format**

**The STATION table is described as follows:**
![image](https://user-images.githubusercontent.com/90106232/190918416-fd864ded-6b4a-4b75-acd2-49815360d094.png)

**where LAT_N is the northern latitude and LONG_W is the western longitude.**

# solution 
```sql
select distinct city 
from station 
where upper(substr(city,1,1)) not in ('a','e','i','o','u')
and lower(substr(city,1,1))  not in ('a','e','i','o','u')
 ```
![image](https://user-images.githubusercontent.com/90106232/190918467-dde10b14-4cfd-4f55-b5e2-00557474fddf.png)


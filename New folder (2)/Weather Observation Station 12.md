## Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

**Input Format**

**The STATION table is described as follows:**

![image](https://user-images.githubusercontent.com/90106232/190917906-98d2dba3-c516-49f3-ab39-f7e4a937f38c.png)

**where LAT_N is the northern latitude and LONG_W is the western longitude.**

```sql
select distinct city from station 
where lower(substr(city,1,1)) not in ('a','e','i','o','u')  and 
lower(substr(city,length(city),1)) not in ('a','e','i','o','u')
```

![image](https://user-images.githubusercontent.com/90106232/190917969-0528eae4-df2b-413b-8eaf-9ef62f2546cc.png)

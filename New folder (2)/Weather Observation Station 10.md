## Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.
**Input Format**
**The STATION table is described as follows:**

![image](https://user-images.githubusercontent.com/90106232/190918205-6df776f4-5bf8-4cf0-91c5-178e02861a31.png)

**where LAT_N is the northern latitude and LONG_W is the western longitude.**
# Solution 

```sql
select distinct city from station 
where 
upper(substr(city ,
length(city),1)) not in ('a','e','i','o','u') and 
lower(substr(city , length(city),1)) 
not in ('a','e','i','o','u')
```

![image](https://user-images.githubusercontent.com/90106232/190918273-b8ac4900-f2b0-49c3-9ad2-95023e91afbe.png)

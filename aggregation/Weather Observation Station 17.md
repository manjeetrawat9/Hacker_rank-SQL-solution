#### Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than . Round your answer to  decimal places.

#### Input Format

### The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190969874-fe5ec867-c1e5-46d8-a2c0-6d007ea7fc08.png)

# Solution
```sql
select round(long_w,4)
from station 
where lat_n = (select min(lat_n) from station where lat_n > 38.7780)
```

![image](https://user-images.githubusercontent.com/90106232/190969966-1eb830b1-55a7-4e16-89d7-73d4547875f4.png)


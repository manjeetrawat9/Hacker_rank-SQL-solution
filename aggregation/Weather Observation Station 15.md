#### Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than . Round your answer to  decimal places.

#### Input Format

#### The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190968976-2f10b9ad-da26-401d-8487-ee31d469dba7.png)

# Solution 

```sql
SELECT ROUND(LONG_W,4) FROM STATION WHERE LAT_N = (SELECT MAX(LAT_N) FROM STATION WHERE LAT_N < 137.2345);
```

![image](https://user-images.githubusercontent.com/90106232/190969113-ab91da42-fe9a-4076-9bcb-2d5614297aa1.png)


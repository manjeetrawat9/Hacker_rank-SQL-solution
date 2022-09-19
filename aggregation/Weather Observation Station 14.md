## Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than . Truncate your answer to  decimal places.

## Input Format

## The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190968700-06493c1a-39a0-45e9-b4a4-d66f6fed6928.png)

### where LAT_N is the northern latitude and LONG_W is the western longitude.

# Solution

```sql
select round(max(lat_n),4) from station where lat_n< 137.2345;
```

![image](https://user-images.githubusercontent.com/90106232/190968826-13772d5c-497a-4a78-bf31-49a2082aaf40.png)

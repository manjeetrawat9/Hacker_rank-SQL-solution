####  A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to  decimal places.

##### Input Format

#### The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190970841-648473bf-b699-4ffc-98de-30e721fa5c9b.png)

#### where LAT_N is the northern latitude and LONG_W is the western longitude.

# Solution

```sql
SELECT ROUND (LAT_N,4)

FROM ( SELECT
ROW_NUMBER() OVER (ORDER BY LAT_N DESC) AS ROWNUMBER,id, LAT_N FROM STATION ) 
AS LAT_N

where ROWNUMBER = ( SELECT ((COUNT(id) + 1) /2) 
       FROM STATION)
```

![image](https://user-images.githubusercontent.com/90106232/190971042-ff99b663-fc3e-4508-9df8-810a6b52917b.png)

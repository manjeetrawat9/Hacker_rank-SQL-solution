### Consider  and  to be two points on a 2D plane.

 **happens to equal the minimum value in Northern Latitude (LAT_N in STATION).**
 **happens to equal the minimum value in Western Longitude (LONG_W in STATION).**
 **happens to equal the maximum value in Northern Latitude (LAT_N in STATION).**
 **happens to equal the maximum value in Western Longitude (LONG_W in STATION).**
**Query the Manhattan Distance between points  and  and round it to a scale of  decimal places.**

**Input Format**

**The STATION table is described as follows:**

![image](https://user-images.githubusercontent.com/90106232/190970230-ed1b7717-33c9-4a02-86bc-6df9902a2f53.png)

#### where LAT_N is the northern latitude and LONG_W is the western longitude.

# Solution

```sql
select round((c-a)+(d-b),4) from
(select min(lat_n) as a,min(long_w) as b,max(lat_n) as c,
max(long_w) as d from station) as df
```
![image](https://user-images.githubusercontent.com/90106232/190970372-ca0b8faf-4b8b-4485-866a-f6c63edd49da.png)

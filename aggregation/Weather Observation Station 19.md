#### Consider  and  to be two points on a 2D plane where  are the respective minimum and maximum values of Northern Latitude (LAT_N) and  are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

#### Query the Euclidean Distance between points  and  and format your answer to display  decimal digits.

##### Input Format

#### The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190970603-18429a4c-5322-4975-bfad-33cb2e61c815.png)

#### where LAT_N is the northern latitude and LONG_W is the western longitude.

# Solution

```sql
select round(sqrt(power((max(lat_n)- min(lat_n)),2)+ power((max(long_w)- min(long_w)),2)),4) from station 
```

![image](https://user-images.githubusercontent.com/90106232/190970724-1adb6463-cf4d-4e78-8933-6e7ea41466f4.png)

### Query the smallest Northern Latitude (LAT_N) from STATION that is greater than . Round your answer to  decimal places.

#### Input Format

#### The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190969325-f2252ddf-c544-44e4-a318-a03128f404a7.png)

**where LAT_N is the northern latitude and LONG_W is the western longitude.**

# Solution

```sql
select round(min(lat_n),4) as lat_hj from station where lat_n > 38.7780
```

![image](https://user-images.githubusercontent.com/90106232/190969528-e395df95-e0b5-40d0-b111-e08059a09fab.png)

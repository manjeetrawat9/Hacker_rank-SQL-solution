### Query the total population of all cities in CITY where District is California.

### Input Format

### The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190968042-0ac7edeb-2716-40ba-866e-c1d3a8319167.png)

# SOlution
```sql
SELECT SUM(POPULATION) FROM CITY WHERE DISTRICT = "California"
```

------------------------------------------------------------------------------------------------------------------------------------------------------
## Revising Aggregations - Averages


---------------------------------------------------------------------------------------------------------------------------------------------------------


## Query the average population of all cities in CITY where District is California.

## Input Format

## The CITY table is described as follows:


![image](https://user-images.githubusercontent.com/90106232/190968042-0ac7edeb-2716-40ba-866e-c1d3a8319167.png)

# Solution

```sql
select avg(population) from city where district = 'California'
```


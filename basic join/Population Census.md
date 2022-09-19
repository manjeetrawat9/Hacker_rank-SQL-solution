## Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

#### Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

#### Input Format

#### The CITY and COUNTRY tables are described as follows:

![image](https://user-images.githubusercontent.com/90106232/190965251-292cbb36-2e6b-4673-a813-167ac3d631a0.png)

![image](https://user-images.githubusercontent.com/90106232/190965317-7d7fe912-a399-47d3-8fa0-f72a2b7932fa.png)

# Solution

```sql
select sum(city.population) as behfkfihl
from  city join country on city.countrycode = country.code 
where country.continent = 'Asia'
```

![image](https://user-images.githubusercontent.com/90106232/190965412-c492ee6d-3077-4f2e-bef0-b1a773b653e6.png)

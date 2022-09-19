#### Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

#### Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

#### Input Format

#### The CITY and COUNTRY tables are described as follows:

![image](https://user-images.githubusercontent.com/90106232/190965645-17d03349-4c77-4ba5-876c-f9215f245396.png)

![image](https://user-images.githubusercontent.com/90106232/190965702-af028eaa-9e4a-4b0e-9fa5-36aa2c93b6e2.png)

# Solution
```sql
select city.name 
from city  join country  on city.countrycode = country.code
where country.continent = 'Africa'
```
![image](https://user-images.githubusercontent.com/90106232/190965833-f239b207-3b24-4f67-a366-263bc747e5ca.png)


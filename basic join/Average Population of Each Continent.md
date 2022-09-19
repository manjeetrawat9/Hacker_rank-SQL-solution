#### Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

#### Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

#### Input Format

#### The CITY and COUNTRY tables are described as follows:

![image](https://user-images.githubusercontent.com/90106232/190965992-11650e0c-c637-4d74-ac4c-45e474fe0b63.png)

![image](https://user-images.githubusercontent.com/90106232/190966029-58a36ebc-9fee-4b88-b634-a2fa5879b050.png)

# Solution

```sql
select country.continent , floor(avg(city.population))
from city join country on city.countrycode = country.code
group by 1

```

![image](https://user-images.githubusercontent.com/90106232/190966115-baa07060-ce43-4744-b441-fb1b9630f440.png)

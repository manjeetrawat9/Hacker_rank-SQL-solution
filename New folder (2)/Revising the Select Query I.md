## Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

## The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/90106232/190916480-77c8db13-8e02-4125-8bca-26e3b3ac0a1c.png)

```sql
select * from city 
where population > 100000 and countrycode = "USA"
```

![image](https://user-images.githubusercontent.com/90106232/190916541-c8518aea-a2bf-461d-bc95-1c44b2458e38.png)


# Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

**The CITY table is described as follows:**

![image](https://user-images.githubusercontent.com/90106232/190916682-e009ddbd-ee3b-4a99-9013-8a934900d998.png)

# Solution

```sql 
select name from city 
where population > 120000 and countrycode="usa"
```

![image](https://user-images.githubusercontent.com/90106232/190916725-3560354b-b5e2-4616-9aca-219fb697542d.png)

**Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.**

**Note: Print NULL when there are no more names corresponding to an occupation.**

**Input Format**

**The OCCUPATIONS table is described as follows:*8

![image](https://user-images.githubusercontent.com/90106232/190962912-6fa5b143-41f1-478a-bfe3-33abfb733696.png)

**Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190963068-26037232-b187-43a8-89ad-6a27b7acc5a1.png)

```sql
with a as (select *, row_number() over (partition by occupation order by name) as w from occupations),
e as (select name,w from a where occupation = 'Doctor'),
b as (select name,w from a where occupation = 'Professor'),
c as (select name,w from a where occupation = 'Singer'),
d as (select name,w from a where occupation = 'Actor')

select e.name,b.name,c.name ,d.name from b left join e on e.w=b.w 
left join c on b.w = c.w
left join d on b.w = d.w
```
![image](https://user-images.githubusercontent.com/90106232/190963174-3b11ac9c-2162-40a4-a2f1-fd4f0a8fa6d2.png)



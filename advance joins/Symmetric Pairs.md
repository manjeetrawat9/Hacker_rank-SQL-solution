## You are given a table, Functions, containing two columns: X and Y.

![image](https://user-images.githubusercontent.com/90106232/190918945-60c0d00f-6dee-40d9-bb49-18302c34be8b.png)


**Two pairs (X1, Y1) and (X2, Y2) are said to be symmetric pairs if X1 = Y2 and X2 = Y1.**

**Write a query to output all such symmetric pairs in ascending order by the value of X. List the rows such that X1 ≤ Y1.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190918973-19f81aa7-a68e-4683-85de-27412715890b.png)

# solution 

```sql
select  a.x, a.y 
from functions as a join functions as b 
on  a.x = b.y and b.x = a.y
where a.x <= a.y
group by 1,2
having count(*) >1 or a.x < a.y
order by a.x
```

![image](https://user-images.githubusercontent.com/90106232/190919062-60435456-0fe9-4bdd-a60b-e69178d6ccb5.png)

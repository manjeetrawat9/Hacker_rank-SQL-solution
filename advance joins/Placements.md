## You are given three tables: Students, Friends and Packages. Students contains two columns: ID and Name. Friends contains two columns: ID and Friend_ID (ID of the ONLY best friend). Packages contains two columns: ID and Salary (offered salary in $ thousands per month).

![image](https://user-images.githubusercontent.com/90106232/190918818-99509c45-2609-4762-9efb-e83034d0f7fd.png)

**Write a query to output the names of those students whose best friends got offered a higher salary than them. Names must be ordered by the salary amount offered to the best friends. It is guaranteed that no two students got same salary offer.**

**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190918853-723b9c97-05ac-445c-b5f9-e14ce33fb9fd.png)

# solution

```sql

select  s.name
from students as s join packages as p on p.id = s.id 
join friends as f on f.id = s.id 
join packages as p2 on f.friend_id = p2.id
where p.salary < p2.salary 

order by p2.salary
```

![image](https://user-images.githubusercontent.com/90106232/190918886-18bf9e74-8287-4e86-bd7a-c2eb8c3bcd9d.png)

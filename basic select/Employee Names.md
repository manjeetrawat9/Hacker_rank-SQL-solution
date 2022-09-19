## Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
**Input Format**
**The Employee table containing employee data for a company is described as follows:**

![image](https://user-images.githubusercontent.com/90106232/190917406-460a7c87-9414-40a6-9e28-6804bda10240.png)

**where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190917429-d297bfd8-4cca-4745-995a-e38020a814d9.png)
# solution
```sql
select name from employee order by name
```

![image](https://user-images.githubusercontent.com/90106232/190917474-4d1b1413-2cb8-455e-90b5-34fab5335901.png)

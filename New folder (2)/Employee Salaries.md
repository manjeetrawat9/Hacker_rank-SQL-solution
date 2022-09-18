## Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than  per month who have been employees for less than  months. Sort your result by ascending employee_id.

**Input Format**

**The Employee table containing employee data for a company is described as follows**
![image](https://user-images.githubusercontent.com/90106232/190917236-48819609-bf49-4233-bd98-5e3558842b56.png)


**where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.**
**Sample Input**
![image](https://user-images.githubusercontent.com/90106232/190917247-22f4fc5c-ac0b-4287-afe2-0fe722ebcf23.png)

# Solution
```sql
select name from employee where salary >2000 and months <10
```

![image](https://user-images.githubusercontent.com/90106232/190917311-2aa30ca4-bd17-4fd5-b75f-a05748582365.png)

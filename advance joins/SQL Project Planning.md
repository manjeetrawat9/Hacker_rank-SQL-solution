## You are given a table, Projects, containing three columns: Task_ID, Start_Date and End_Date. It is guaranteed that the difference between the End_Date and the Start_Date is equal to 1 day for each row in the table.

![image](https://user-images.githubusercontent.com/90106232/190918592-bc445bfd-8ff2-4716-9624-f113071f386d.png)

**If the End_Date of the tasks are consecutive, then they are part of the same project. Samantha is interested in finding the total number of different projects completed.**
**Write a query to output the start and end dates of projects listed by the number of days it took to complete the project in ascending order. If there is more than one project that have the same number of completion days, then order by the start date of the project.**
**Sample Input**
![image](https://user-images.githubusercontent.com/90106232/190918604-32e5fafb-fb56-469c-ab11-9dffaaaa9eef.png)

# solution

```sql
select start_date as desire,min(end_date) from (select start_date, end_date from 
(
    select start_date from (select start_date,start_date -lag(start_date,1) over(order by start_date) as df  from projects ) as cf
 where df > 1 or df is null
) as c 
 join 
(
    select end_date from (select end_date,lead(end_date,1) over(order by end_date)-end_date as dfff  from projects
) as dfc where dfff >1 or dfff is null

) as d 
 on start_date < end_date) as don
 group by 1
order by min(end_date)-start_date,1
 ```
 
 ![image](https://user-images.githubusercontent.com/90106232/190918716-a609f75a-fef3-4b48-be91-7bad052bd164.png)

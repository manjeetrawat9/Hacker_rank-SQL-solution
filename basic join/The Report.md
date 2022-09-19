## You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

![image](https://user-images.githubusercontent.com/90106232/190966268-573407fd-dd83-429e-86d8-f4471471cb05.png)

#### Grades contains the following data:
![image](https://user-images.githubusercontent.com/90106232/190966336-9361436e-c36b-4177-8b0a-552d2c0657d2.png)

**Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.**

**Write a query to help Eve.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190966447-fcbe973c-95e4-41a8-a86a-ab2d11950efa.png)

# solution
```sql
SELECT CASE WHEN grd.grade < 8 THEN NULL WHEN grd.grade >= 8 THEN std.name END,grd.grade, std.marks FROM students std, grades grd WHERE std.marks BETWEEN grd.min_mark AND grd.max_mark ORDER BY grd.grade DESC, std.name ASC;
```

![image](https://user-images.githubusercontent.com/90106232/190966538-2c14eb60-40cc-4ac9-8cda-4a5e0ad09d53.png)

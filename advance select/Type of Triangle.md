## Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

**Equilateral: It's a triangle with  sides of equal length.**
**Isosceles: It's a triangle with  sides of equal length.**
**Scalene: It's a triangle with  sides of differing lengths.**
**Not A Triangle: The given values of A, B, and C don't form a triangle.**
**Input Format**

**The TRIANGLES table is described as follows:**
![image](https://user-images.githubusercontent.com/90106232/190961957-01da0ab5-eb77-4e3b-99d3-9840e4555efa.png)

**Each row in the table denotes the lengths of each of a triangle's three sides.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190962070-0bb8823b-7059-467b-a4e4-2a0011c22433.png)

# solution
```sql
select case when a+b > c and b+c > a and c+a > b then
( case when a= b and b= c and c=a then 'Equilateral'
when a =b or b=c or c=a then 'Isosceles'
when a <> b and b <>c and c<> a then 'Scalene' end )
else ' Not A Triangle' end
from triangles
```

![image](https://user-images.githubusercontent.com/90106232/190962206-a865ac7a-eaae-4b3f-83a1-220336e407d3.png)

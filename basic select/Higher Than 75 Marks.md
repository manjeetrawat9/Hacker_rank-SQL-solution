## Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

**Input Format**

**The STUDENTS table is described as follows:**
![image](https://user-images.githubusercontent.com/90106232/190917557-a8ed5476-1c49-424f-9bc9-9ab386e39e5c.png)

**The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.**
**Sample Input**

![image](https://user-images.githubusercontent.com/90106232/190917600-30ff38fa-93b7-4f08-919a-b6ba83dfa4b1.png)

# Solution

```sql
select name from students 
where marks >75 
order by right(name,3), id
```

![image](https://user-images.githubusercontent.com/90106232/190917637-0a17e900-7b57-410d-b448-8de94a52f2f2.png)

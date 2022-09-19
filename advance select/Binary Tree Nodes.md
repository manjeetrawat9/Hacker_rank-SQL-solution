## You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

![image](https://user-images.githubusercontent.com/90106232/190963294-7ca5e903-5ff1-4fcd-9eab-70d5c433822f.png)

**Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:**

**Root: If node is root node.**
**Leaf: If node is leaf node.**
**Inner: If node is neither root nor leaf node.**

**Sample input:**

![image](https://user-images.githubusercontent.com/90106232/190963410-63cfa512-97af-4d8e-aaf3-c686e8be1671.png)

```sql
/*
select n, case when n not in (p) then 'root' else 'inner' end from bst
*/

select n, case when p is null then 'Root'
when n in (select p from bst) then 'Inner'
else  'Leaf' end from bst
order by 1
```

![image](https://user-images.githubusercontent.com/90106232/190963541-4ac3318a-6feb-47fd-9e4e-8a1d5560f3dc.png)

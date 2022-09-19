### You did such a great job helping Julia with her last coding contest challenge that she wants you to work on this one, too!

**The total score of a hacker is the sum of their maximum scores for all of the challenges. Write a query to print the hacker_id, name, and total score of the hackers ordered by the descending score. If more than one hacker achieved the same total score, then sort the result by ascending hacker_id. Exclude all hackers with a total score of  from your result.**

**Input Format**

**The following tables contain contest data:**
**Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.**

![image](https://user-images.githubusercontent.com/90106232/190966773-ded9e711-0868-4500-aa9d-45e367c8a9e2.png)

**Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge for which the submission belongs to, and score is the score of the submission.**

![image](https://user-images.githubusercontent.com/90106232/190966851-e2b684e1-11a3-486b-a6a3-b150bde4b81a.png)

**Sample input**

![image](https://user-images.githubusercontent.com/90106232/190966940-1230b31b-5f86-489c-b3b7-ad0f3099af0f.png)

![image](https://user-images.githubusercontent.com/90106232/190967018-7474a933-7f14-4be7-8927-d75906b4635b.png)

# Solution

```sql
select h.hacker_id,h.name,aa.df from 
(select hacker_id, sum(tot) as df from 
 (select hacker_id, challenge_id,max(score) as tot from submissions group by 1,2) as a group by 1 having  sum(tot) <> 0) as aa join hackers as h on h.hacker_id = aa.hacker_id
order by aa.df desc, h.hacker_id
```

![image](https://user-images.githubusercontent.com/90106232/190967204-38565455-26b6-4e2d-96af-cb02f9397aaa.png)

## Samantha interviews many candidates from different colleges using coding challenges and contests. Write a query to print the contest_id, hacker_id, name, and the sums of total_submissions, total_accepted_submissions, total_views, and total_unique_views for each contest sorted by contest_id. Exclude the contest from the result if all four sums are .

**Note: A specific contest can be used to screen candidates at more than one college, but each college only holds  screening contest.**

**Input Format**

**The following tables hold interview data:**

**Contests: The contest_id is the id of the contest, hacker_id is the id of the hacker who created the contest, and name is the name of the hacker.**

![image](https://user-images.githubusercontent.com/90106232/190919132-d3e4f3e6-29c9-444f-bcdf-96cd7f0cab82.png)

**Colleges: The college_id is the id of the college, and contest_id is the id of the contest that Samantha used to screen the candidates.**

![image](https://user-images.githubusercontent.com/90106232/190919154-1bbc8325-0eee-4257-848e-201f6d9f3b6a.png)

**Challenges: The challenge_id is the id of the challenge that belongs to one of the contests whose contest_id Samantha forgot, and college_id is the id of the college where the challenge was given to candidates.**

![image](https://user-images.githubusercontent.com/90106232/190919174-e55e26f8-8e06-4fc3-b1d2-a70ab9352104.png)

**View_Stats: The challenge_id is the id of the challenge, total_views is the number of times the challenge was viewed by candidates, and total_unique_views is the number of times the challenge was viewed by unique candidates.**

![image](https://user-images.githubusercontent.com/90106232/190919193-cf2237f8-6e4e-454f-97b8-78b4e0215ef6.png)

**Submission_Stats: The challenge_id is the id of the challenge, total_submissions is the number of submissions for the challenge, and total_accepted_submission is the number of submissions that achieved full scores.**

![image](https://user-images.githubusercontent.com/90106232/190919205-55d3ae5f-5fde-47d7-bc60-d54c54d5e528.png)

# solution
```sql
select con.contest_id,
con.hacker_id, 
con.name, 
sum(total_submissions), 
sum(total_accepted_submissions), 
sum(total_views), sum(total_unique_views)
from contests con 
join colleges col on con.contest_id = col.contest_id 
join challenges cha on  col.college_id = cha.college_id 
left join
(select challenge_id, sum(total_views) as total_views, sum(total_unique_views) as total_unique_views
from view_stats group by challenge_id) vs on cha.challenge_id = vs.challenge_id 
left join
(select challenge_id, sum(total_submissions) as total_submissions, sum(total_accepted_submissions) as total_accepted_submissions from submission_stats group by challenge_id) ss on cha.challenge_id = ss.challenge_id
group by con.contest_id, con.hacker_id, con.name
having sum(total_submissions)!=0 or 
sum(total_accepted_submissions)!=0 or
sum(total_views)!=0 or
sum(total_unique_views)!=0
order by contest_id;
```

![image](https://user-images.githubusercontent.com/90106232/190919244-259f917b-bb39-4d8c-8176-8dce7e068de5.png)

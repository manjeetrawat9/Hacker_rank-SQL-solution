## Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy: 

![image](https://user-images.githubusercontent.com/90106232/190963788-b5ec5687-5965-4bc7-ab8e-2dcb1c537c79.png)

## Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.
**Note:**

**The tables may contain duplicate records.**
**The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.**
**Input Format**

**The following tables contain company data:**
**Company: The company_code is the code of the company and founder is the**

![image](https://user-images.githubusercontent.com/90106232/190963933-6fa709e5-00f8-4871-abc9-c25aef5cc66a.png)

**Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.**

![image](https://user-images.githubusercontent.com/90106232/190964019-161fe2f9-d351-4f30-a207-fc1e18448d81.png)

**Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the**

![image](https://user-images.githubusercontent.com/90106232/190964120-27041699-6f56-4a8d-b002-19f3b9e0b692.png)

**Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.**

![image](https://user-images.githubusercontent.com/90106232/190964210-62fe0ae6-2d86-409e-9e50-a7a1e8111ba7.png)

**Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.**

![image](https://user-images.githubusercontent.com/90106232/190964300-0b96c6eb-8050-4622-96bd-b07da1688980.png)

# Solution

```sql
select c.company_code, c.founder, count(distinct l.lead_manager_code), count(distinct s.senior_manager_code),count(distinct m.manager_code),count(distinct e.employee_code)
from
Company as c inner join Lead_Manager as l on c.company_code = l.company_code 
inner join 
Senior_Manager as s on l.lead_manager_code = s.lead_manager_code 
inner join Manager as m  on m.senior_manager_code = s.senior_manager_code
inner join Employee as e on e.manager_code = m.manager_code 
group by c.company_code, c.founder order by c.company_code;
```

![image](https://user-images.githubusercontent.com/90106232/190964750-21ed2c40-0874-41c9-af3c-ca13b0dd2764.png)

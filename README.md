# window-functions

```
	-- use it in select statement
select  name ,department,age ,(select avg (salary ) from employees)
from employees
```
```
use it in from statement
	-- average number of people per department
	select department, avg(num_workers) from(
			 select department , count(*) as num_workers
			 from employees
			 group by department) 
	 group by 1
```

```
use it in where statement
--which employees are earning more than the average salary
select name ,department,salary
from employees e
where salary >
	(
	select avg(salary)
	from employees
	where department =e.department)
select department,avg(salary) 
from employees 
group by department
```

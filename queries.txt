
create view query1 as 
select e.emp_no , e.first_name, e.last_name, e.sex, s.salary 
from employees as e
inner join salaries as s
on e.emp_no = s.emp_no;


create view query2 as 
select first_name, last_name, hire_date from employees 
where hire_date >= '1986-01-01' 
AND hire_date <='1986-12-31';

create view query3 as 
select d.dept_no, d.dept_name ,m.emp_no, e.first_name, e.last_name
from departments as d
inner join dept_manager as m
on d.dept_no = m.dept_no
inner join employees as e
on e.emp_no = m.emp_no
order by d.dept_name;


create view query4 as 
select e.emp_no,  e.last_name, e.first_name, d.dept_name
from employees as e
inner join dept_emp as de
on de.emp_no = e.emp_no
inner join departments as d
on de.dept_no = d.dept_no;

create view query5 as 
select first_name, last_name, sex
from employees
where first_name = 'Hercules'
and
last_name like 'B%';

create view query6 as
select emp_no, last_name, first_name, dept_name from query3
where dept_name = 'Sales';

create view query7 as 
select emp_no, last_name, first_name, dept_name from query3
where dept_name in( 'Sales', 'Development');

create view query8 as 
select last_name, count(last_name) as frequency
from employees
group by last_name
order by frequency desc;


select * from query1;
select * from query2;
select * from query3;
select * from query4;
select * from query5;
select * from query5;
select * from query7;
select * from query8;


select * from employees where emp_no = '499942'


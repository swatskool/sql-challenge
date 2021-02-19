create table Departments (
	dept_no varchar primary key,
	dept_name varchar not null 
	);
create table titles(
	title_id varchar primary key,
	title varchar
);

create table employees (
	emp_no varchar primary key,
	emp_title_id varchar not null,
	birth_date date not null,
	first_name varchar not null,
	last_name varchar not null,
	sex varchar not null,
	hire_date date not null,
	foreign key (emp_title_id) references titles(title_id)
);


create table dept_emp (
	emp_no varchar not null ,
	dept_no varchar not null ,
	primary key (dept_no,emp_no),
	foreign key (dept_no) references departments(dept_no),
	foreign key (emp_no) references employees(emp_no)
);

create table dept_manager (
	manager_id serial primary key,
	dept_no varchar not null,
	emp_no varchar not null,
	foreign key (dept_no) references departments(dept_no),
	foreign key (emp_no) references employees(emp_no)
);



create table salaries(
	id serial primary key,
	emp_no varchar,
	salary int,
	foreign key (emp_no) references employees(emp_no)
	
);

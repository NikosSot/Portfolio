**Project description**

In this scenario, I need to obtain specific information about employees, their machines, and the departments they belong to from the database.

My team needs data to investigate potential security issues and to update computers.

I am responsible for filtering the required information from the database.

Here’s how I’ll do this task: First, I’ll retrieve all failed login attempts after business hours. Second, I’ll retrieve all login attempts that occurred on specific dates. Third, I’ll retrieve logins that didn't originate in Mexico. Fourth, I’ll retrieve information about certain employees in the Marketing department. Fifth, I’ll retrieve information about employees in the Finance or the Sales department. Finally, I’ll obtain information about employees who are not in the Information Technology department.


**Retrieve after hours failed login attempts**

My team is investigating failed login attempts that were made after business hours. I want to retrieve this information from the login activity. I’ll identify all unsuccessful attempts after 18:00.

The login_time column in the log_in_attempts table contains information on when login attempts were made. Office hours end at '18:00'.

The following code demonstrates how I created a SQL query to filter for failed login attempts
that occurred after business hours.

<img width="886" height="501" alt="Screenshot 2026-06-08 130405" src="https://github.com/user-attachments/assets/1d61aa37-eeaa-4604-a235-c7a85789d3da" />
First, I started by selecting all
data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to
filter my results to output only login attempts that occurred after 18:00 and were unsuccessful.
The first condition is login_time > '18:00', which filters for the login attempts that
occurred after 18:00. The second condition is success = FALSE, which filters for the failed
login attempts.
According to my data, 19 failed attempts have been made after 18:00.


**Retrieve login attempts on specific dates**

My team is investigating a suspicious event that occurred on '2022-05-09'. I need to retrieve all login attempts that occurred on this day and the day before ('2022-05-08').

The login_date column in the log_in_attempts table contains information on the dates when login attempts were made.

The following code demonstrates how I created a SQL query to filter for login attempts that
occurred on specific dates.

<img width="831" height="773" alt="11111" src="https://github.com/user-attachments/assets/11f806fb-9a44-4a47-82d3-ad4ac4fc7c20" />
<img width="877" height="846" alt="22222" src="https://github.com/user-attachments/assets/2a20c03a-b3f7-4a9c-b947-68e9dafa15ef" />

This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by
selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR
operator to filter my results to output only login attempts that occurred on either 2022-05-09
or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins
on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for
logins on 2022-05-08.

According to the data there are 75 login attempts in these two days.

**Retrieve login attempts outside of Mexico**

After investigating the organization’s data on login attempts, I believe there is an issue with the
login attempts that occurred outside of Mexico. These login attempts should be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that
occurred outside of Mexico.

<img width="830" height="851" alt="33333" src="https://github.com/user-attachments/assets/71be715b-e59a-4cde-a6cf-7f54326eb143" />
<img width="876" height="829" alt="4444" src="https://github.com/user-attachments/assets/872df14c-0ced-4c03-9473-597f55ca5ac3" />
<img width="879" height="839" alt="555" src="https://github.com/user-attachments/assets/18a59247-ce2c-494d-98db-31b4a8912776" />

This query returns all login attempts that occurred in countries other than Mexico. First, I started by
selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to
filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because
the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any
number of unspecified characters when used with LIKE.

According to my data there were 144 login attempts made outside of Mexico.


**Retrieve employees in Marketing**

My team wants to update the computers for certain employees in the Marketing department.
To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines
from employees in the Marketing department in the East building.

<img width="736" height="303" alt="image" src="https://github.com/user-attachments/assets/5fa025d5-d5f2-45c0-9b5f-fc14f76338e0" />

The first part of the screenshot is my query, and the second part is a portion of the output. This
query returns all employees in the Marketing department in the East building. First, I started by
selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for
employees who work in the Marketing department and in the East building. I used LIKE with
East% as the pattern to match because the data in the office column represents the East
building with the specific office number. The first condition is the department =
'Marketing' portion, which filters for employees in the Marketing department. The second
condition is the office LIKE 'East%' portion, which filters for employees in the East
building.


**Retrieve employees in Finance or Sales**

The machines for employees in the Finance and Sales departments also need to be updated.
Since a different security update is needed, I have to get information on employees only from
these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines
from employees in the Finance or Sales departments.

<img width="838" height="845" alt="666" src="https://github.com/user-attachments/assets/ec93f0f8-9f05-425b-83de-42ab6c033d72" />
<img width="701" height="529" alt="777" src="https://github.com/user-attachments/assets/f973412a-a279-480f-924f-64445170fa23" />

This query returns all employees in the Finance and Sales departments. First, I started by selecting
all data from the employees table. Then, I used a WHERE clause with OR to filter for employees
who are in the Finance and Sales departments. I used the OR operator instead of AND because I
want all employees who are in either department. The first condition is department =
'Finance', which filters for employees from the Finance department. The second condition is
department = 'Sales', which filters for employees from the Sales department.


**Retrieve all employees not in IT**

My team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. I should use the NOT operator to identify these employees.

<img width="774" height="852" alt="888" src="https://github.com/user-attachments/assets/82d5957b-4e76-4313-bb61-c2bfe1080dda" />
<img width="872" height="867" alt="999" src="https://github.com/user-attachments/assets/97024ff7-c84e-411f-885a-4aab06136786" />
<img width="859" height="866" alt="1010" src="https://github.com/user-attachments/assets/0faa4956-cad9-48be-bb08-18098d089b52" />
<img width="732" height="362" alt="111111111111" src="https://github.com/user-attachments/assets/a2523367-24a6-476c-ae13-cd8f10ce79cd" />

The query returns all employees not in the Information Technology department. First, I started by
selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for
employees not in this department.

**Summary**

I applied filters to SQL queries to get specific information on login attempts and employee
machines. I used two different tables, log_in_attempts and employees. I used the AND,
OR, and NOT operators to filter for the specific information needed for each task. I also used
LIKE and the percentage sign (%) wildcard to filter for patterns.


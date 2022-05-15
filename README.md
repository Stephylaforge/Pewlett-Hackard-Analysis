# Pewlett-Hackard-Analysis
SQL 
### A report to help the manager prepare for the upcoming "silver tsunami."

## Employee database analysis

Overview of the analysis: Explain the purpose of this analysis.
The first step to getting the correct results ![EmployeeDB](https://user-images.githubusercontent.com/98365309/168454782-df52b61d-11bf-4bd2-89a2-af9c7b177fed.png)
based off the data provided was too merge the data frames between linked common categories. 
See the image below to see the set up for linking the data. 
![Uploading EmployeeDB.png…]()
By linking the data we were able to pull data that was needed to create tables of data that pertained important information for the upcoming Retiring Employees. This contained pulling names, seperating by birth date, and job information.

The first set of data to pull was the Number of Retiring Employees by Title.
We did this by pulling the data based of criteria of
	SELECT e.emp_no,
    e.first_name,
    e.last_name,
	t.title,
	t.from_date,
	t.to_date
INTO retirement_titles
FROM employees as e
LEFT JOIN titles as t
ON (e.emp_no = t.emp_no)
WHERE (birth_date BETWEEN '1952-01-01' AND '1955-12-31')
ORDER BY e.emp_no;

After getting this data into an excel sheet. The next step was to pull distinct counts and remove duplicates and putting them into another table to export to excel. 

![retiring_titles](https://user-images.githubusercontent.com/98365309/168455114-e8487de9-6c79-4f35-a1f2-d25a57998f36.png)

Deliverable 2: The Employees Eligible for the Mentorship Program
The last step after retreiving this data from the tables we pulled is to see which employees would be eligable for the Mentorship program. We did this by using this to pull specific candidates. 
WHERE (e.birth_date BETWEEN '1965-01-01' AND '1965-12-31')

![Mentorship_eligibility](https://user-images.githubusercontent.com/98365309/168455137-de8d298e-b59a-4f74-a694-b59cbc41df5d.png)

## Results
Major points from the two analysis deliverables. 
- There are a lot of different roles that will be retiring and will have to adjust to new hires coming in to replace them.
- Due to multiple rows having upcoming retirement the roles will need to be reviewed for updating training regulations to ensure that the new hires will be continuing the work done to ensure proper work flow.
- This can effect how work is done, the transition periods between retiring employees and the new employees will have to be planned in such a manner to ensure that no employee gets stuck with an extra work load.
- This is great data for the fact when discussing the Employee experience you can conduct exit interviews to gather more data on employee/job needs, chagnes, or to promote how logn employees have stayed with the company & why.

Summary: 
Provide high-level responses to the following questions, then provide two additional queries or tables that may provide more insight into the upcoming "silver tsunami."

How many roles will need to be filled as the "silver tsunami" begins to make an impact?
90,398 roles will need to be filled.

Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
No there aren't enough compared to the amount retiring. The amount to mentor is about only about 1,400 which leaves a lot of room for outsiders to come in and apply. This can lead to people in the work force having to learn quickly, raising salaries due to promotions, or leaving negotiations for new hires.

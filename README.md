# Pewlett-Hackard-Analysis

## Overview of the analysis: 
The purpose of this analysis is to help understand the demographics of Pewlett-Hackard employees who are near retirement.  Specifically, we were asked to provide a breakdown of how many individuals are in the retirement zone (born between 1952 and 1955) by their current job titles.  This required combining information from two separate csv files, filtering by birth date range and since many individuals held several titles over the course of their career, we needed to list these individuals by their most recent job title.  In response to the large number of near term retirees, a second aspect of the analysis involved the identification of employees who are eligible to participate in a newly proposed mentorship program.  Eligibility for this program was defined as people who were born in 1965.

## Results: 
Provide a bulleted list with four major points from the two analysis deliverables. Use images as support where needed.

- There are 90,398 people who are nearing retirement as defined by those people who were born between 1952 and 1955.  We already know from the Employees table that Pewlett-Hackard has 300,024 employees so this represents 30% of PH's workforce.  The number of people nearing retirement was determined by first creating a query that joined the Employees and titles tables, filtering them by the desired date range and creating a new table called retirement_titles. I then used the DISTINCT ON() function to retrieve only the most recent title for employees that had more than one title throughout their career.  This was performed on the retirement_titles table and created a new table called unique_titles which contained emp_no, first_name, last_name, and title.  The code for both of those queries is shown below:
  ![image](https://user-images.githubusercontent.com/90977689/140315685-7c25c42e-12fa-4d24-ba6a-d6f5e6c813ea.png)

The header of the resultant table is shown below:

![image](https://user-images.githubusercontent.com/90977689/140316455-fe0a392b-495b-42f2-bf11-76ab7b542dcb.png)

- Senior Engineer and Senior Staff are the two titles with the highest number of near-retiring people. This was determined by querying the unique_titles table and using the COUNT() function on employees and then grouping by titles and ordering by count in descending order.  This was put into a new table called retiring_titles.  The code and resultant table are shown below:
   ![image](https://user-images.githubusercontent.com/90977689/140317703-f5567130-e8ef-4a6f-bc49-5eb1606c20fb.png)

  ![image](https://user-images.githubusercontent.com/90977689/140317843-6aecd362-000c-4b54-abcd-bfef80bde5b0.png)

- Based on the two tables created above, we can determine that many employees in this age group have not changed jobs over the course of their career.  Since the retirement_titles table captures all of the titles and the retiring_titles captures only the latest titles, simple division of the total counts reveals that in this age range employees have an average of 1.48 job titles.  Or in other words, more than half of this population has never had a promotion or job change.

- Th 

## Summary: 
Provide high-level responses to the following questions, then provide two additional queries or tables that may provide more insight into the upcoming "silver tsunami."

- How many roles will need to be filled as the "silver tsunami" begins to make an impact?
- Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

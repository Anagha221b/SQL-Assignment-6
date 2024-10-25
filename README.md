# SQL-Assignment-6
Task # 6
Scenario--Consider the Country table and Persons table that you created earlier and 
perform the following:
(1)Perform inner join, Left join, and Right join on the tables.
(2)List all distinct country names from both the Country and Persons tables.
(3)List all country names from both the Country and Persons tables, including duplicates.
(4)Round the ratings of all persons to the nearest integer in the Persons table.
1.1—Performing Inner join 
• This query retrieves records that have matching values in both the Persons and 
Country tables based on the Country_Id column.
Advantage of Inner join—Inner join only includes the rows where a match is found in both 
the tables.
--Query to achieve the above advantage
select p.Fname,p.Lname,p.Population,p.Rating,p.Country_Id,p.Country_name,c.Area from 
Persons p
inner join Country c on c.Id=p.Country_Id;
1.2—Performing left join
• This query retrieves all records from the Persons table , and the matched records 
from the Country table . If no match is found , NULL values will be returned for 
columns from the Country Table.
Advantage of Left join—Left join include all then rows from the left table , even if there is 
no corresponding records in the right table.
--Query to achieve the above advantage
select p.Fname,p.Lname,p.Population,p.Rating,p.Country_Id,p.Country_name,c.Area from 
Persons p
Left join Country c on c.Id=p.Country_Id;
1.3—Performing right join
• This query retrieves records from the Country table, and the matched records from 
the Persons Table .If no match is found ,Null values will be returned for columns 
from the Persons Table.
Advantage of Right join—Right join includes all rows from the right table , even if there is 
no corresponding record in the left table.
--Query to achieve the above advantage
select p.Fname,p.Lname,p.Population,p.Rating,p.Country_Id,p.Country_name,c.Area from 
Persons p
Right join Country c on c.Id=p.Country_Id;
2—Performing Union operator to list distinct Country_name from both the Table 
• This query uses the UNION operator to combine country names from both tables. 
The UNION operator removes duplicates, ensuring that each country name appears 
only once in the final result.
Advantage of Union Operator- Distinct ensures that duplicate records are eliminated 
before combining results from both tables.
--Query to achieve above advantage
select distinct Country_name from Country
UNION
select Distinct Country_name from Persons;
3-- Performing Union All operator to list Country_name from both the Table including 
Duplicates.
• This query uses UNION ALL, which combines results from both tables but does not 
eliminate duplicates. If a country name appears in both tables or multiple times 
within one table, it will be repeated in the output.
Advantage of Union All Operator- UNION ALL does not eliminate the duplicates.If we wish 
to include the duplicates in the final output from both the tables we can use Union All 
instead of Union that’s the only basic difference between UNION and UNION ALL
--Query to achieve above advantage
select Country_name from Country
UNION ALL
select Country_name from Persons;
4--Rounding off the ratings of all persons to the nearest integer in the Persons table.
• This query rounds the ratings for each person in the Persons table to the nearest 
whole number using the ROUND() function.
Advantage of ROUND expression-The ROUND(column_name, 0) expression rounds the 
column to desired decimal places .
--Query to achieve above advantage
SELECT Fname,Lname,Country_name,ROUND(Rating,0) AS RoundedRating from Persons;

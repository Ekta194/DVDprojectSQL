# DVDprojectSQL
I have used a pgAdmin to use PostgreSQL database.
Discription of each queries mentions below.

Query--(1)--SELECT and WHERE

This query retrieves the first and last names of actors whose first name is 'Johnny'. 
It helps to identify actors who share the same first name in the database.

Query--(2)--MAX, AVG with sub-query 
This query using  WHERE clause filters with the results of maximum and average amount of payment.
It helps to retrive the data where the customer_id by the significant subquery.

Query--(3)--CONCAT with JOIN
This query retrieves the desired information, including the film title, description,and length with the help of joining the tables with foreign keys.
Using CONCAT helps to make a new column with combine two or more different column name.

Query--(4)--COUNT with INNER JOIN and GROUP BY
This query determines the number of actors in each film using COUNT aggregation function.
It helps to provide insights into  movies with large casts or small casts.

Query--(5)--LEFT JOIN with ORDER BY and LIMIT
This query identifies the top 10 customers who have paid more. 
It helps in identifying high-spending customers with the help of ORDER BY clause.

Query--(6)--COUNT and BETWEEN with GROUP BY and ORDER BY
This query calculates the number of rentals  made during the specific time period of July and August of 2005. 
It helps to identify trends or duration within a year customers are used to spend their time to watch the movies.

Query--(7)--DISTINC on WHERE IN condition
This query identifies unique customers by using DISTINCT clause, who have made payments over 10. 
It helps to target customers who regularly make appreciable(large) payments.

Query--(8)--CASE Statement with GROUP BY
This query calculates the average length of films for each rating category, and classifies them into 'Long' or 'Short' categories based on average length. 
It helps as a evalute term of measures.

Query--(9)--HAVING clause
This query gives the results to include only those groups where the count of 16 is not equal to the length of the title. 

Query--(10)--MIN, MAX(using Aliases),& Wildcard Characters % 
This query retrives the shortest and longest films which starts with 'A'. 
It helps to understand the range of film lengths in a certain situation.

Query--(11)--RIGHT OUTER JOIN ,LIKE & DISTINCT
This query retrive a needed data from city and adress tables under such conditions.
It helps to merge and get a quality data from two or more different kind of tables. 

Query--(12)--RIGHT JOIN, ORDER BY ASC OR DESC
This query retrive the list of all rentals and, for each rental with the customer details sorted by the most recent rental. 
It helps to analyze rental trends and active customers.

Query--(13)--CROSS JOIN, LIMIT
This query retrives a data of a combination of every film title with every category name,with limiting the results for the first 50 records.
It helps to resize the table with demanding classifcation.

Query--(14)--Rank Function
This query uses the RANK() function with the OVER clause to calculate the rank of each city within its respective last_update partition.

Query--(15)--WINDOW Function with Rank
This query retrives a data of a rank to each rental for a particular customer, based on the rental date.The earliest rental has a lowest rank.
It helps to understand rental patterns of customers and frequency of they rented a movie.


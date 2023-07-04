--(1)--SELECT and WHERE
SELECT first_name, last_name FROM actor WHERE first_name = 'Johnny';


--(2)--MAX, AVG with sub-query of 
SELECT (SELECT MAX(p.amount) FROM payment p) AS MAX,
 (SELECT AVG(p.amount) FROM payment p) AS AVG,
 p.payment_id,p.customer_id from payment p 
WHERE p.customer_id=ANY(SELECT c.customer_id FROM customer c WHERE store_id=1);


--(3)--CONCAT with JOIN
SELECT CONCAT(a.first_name,' ',a.last_name) as full_name,
f.title, f.description, f.length
FROM actor a
JOIN film_actor fa ON a.actor_id=fa.actor_id
JOIN film f ON f.film_id=fa.film_id;


--(4)--COUNT with INNER JOIN and GROUP BY
SELECT film.title, COUNT(actor.actor_id) as actor_count
FROM film
INNER JOIN film_actor ON film.film_id = film_actor.film_id
INNER JOIN actor ON actor.actor_id = film_actor.actor_id
GROUP BY film.title;


--(5)--LEFT JOIN with ORDER BY and LIMIT
SELECT customer.customer_id, customer.first_name, customer.last_name, payment.amount
FROM customer
LEFT JOIN payment ON customer.customer_id = payment.customer_id
ORDER BY payment.amount DESC
LIMIT 10;


--(6)--COUNT and BETWEEN with GROUP BY and ORDER BY
SELECT customer_id , count(*) AS Rental_Count
FROM rental
WHERE rental_date BETWEEN '2005-07-01' AND '2005-08-31'
GROUP BY customer_id
ORDER BY Rental_Count DESC;


--(7)-- DISTINC on WHERE IN condition
SELECT DISTINCT customer_id
FROM rental
WHERE customer_id IN (SELECT customer_id FROM payment WHERE amount > 10);


--(8)--CASE Statement with GROUP BY
SELECT rating, 
       AVG(length) AS avg_length, 
       CASE 
         WHEN AVG(length) > 120 THEN 'Long'
         ELSE 'Short'
       END AS film_length_category
FROM film 
GROUP BY rating;


--(9)--HAVING clause
SELECT f.film_id, f.title
FROM film f
JOIN inventory i ON f.film_id = i.film_id
JOIN rental r ON i.inventory_id = r.inventory_id
JOIN payment p ON r.rental_id = p.rental_id
GROUP BY f.film_id HAVING COUNT(16)<>LENGTH(title);


--(10)--MIN, MAX(using Aliases),& Wildcard Characters % 
SELECT MIN(length) as min_length, MAX(length) as max_length
FROM film
WHERE title LIKE 'A%';

 
--(11)--RIGHT OUTER JOIN ,LIKE & DISTINCT
SELECT c.city_id,c.city,c.country_id,a.district,a.postal_code 
FROM city 
c RIGHT OUTER JOIN address a ON c.city_id=a.city_id 
WHERE city LIKE 'C%' AND country_id=ANY(SELECT DISTINCT c.country_id FROM city c);


--(12)--RIGHT JOIN, ORDER BY ASC OR DESC
SELECT customer.customer_id, customer.first_name, customer.last_name, rental.rental_id
FROM customer
RIGHT JOIN rental ON customer.customer_id = rental.customer_id
ORDER BY rental.rental_date DESC;


--(13)--CROSS JOIN, LIMIT
SELECT film.title, category.name
FROM film
CROSS JOIN category
LIMIT 50;


--(14)--Rank Function
SELECT city_id,last_update, city,
RANK()OVER(PARTITION BY last_update ORDER BY country_id ASC) 
FROM city GROUP BY city_id HAVING city LIKE 'B%'


--(15)--WINDOW Function with Rank
SELECT rental_id, customer_id, rental_date, 
       RANK() OVER (PARTITION BY customer_id ORDER BY rental_date) as rental_rank
FROM rental;


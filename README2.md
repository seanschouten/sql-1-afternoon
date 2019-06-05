CREATE TABLE person (person_id SERIAL, 
                     name VARCHAR, 
                     age INTEGER, 
                     height INTEGER,
                     city VARCHAR,
                     favorite_color VARCHAR);

INSERT INTO person ( name, age, height, city, favorite_color )
VALUES ('Bub Hatch', 38, 195, 'Salt Lake City', 'Orange'); 

INSERT INTO person ( name, age, height, city, favorite_color )
VALUES ('Dana Davis', 50, 120, 'Murray', 'Blue');

INSERT INTO person ( name, age, height, city, favorite_color )
VALUES ('Connor Cannon', 28, 172, 'Sandy', 'Pink');

INSERT INTO person ( name, age, height, city, favorite_color )
VALUES ('Clay Layton', 34, 185, 'West Jordan', 'Blue');

INSERT INTO person ( name, age, height, city, favorite_color )
VALUES ('Johnny Norman', 42, 155, 'Murray', 'Black');                     

SELECT * FROM person ORDER BY height desc;

SELECT * FROM person ORDER BY height asc;

SELECT * FROM person ORDER BY age desc;

SELECT * FROM person WHERE age < 20;

SELECT * FROM person WHERE age = 18;

SELECT * FROM person WHERE age < 20 OR age > 30;

SELECT * FROM person WHERE age != 27;

SELECT * FROM person WHERE favorite_color != 'red';

SELECT * FROM person WHERE favorite_color != 'red' AND favorite_color != 'Blue';

SELECT * FROM person WHERE favorite_color = 'Orange' OR favorite_color = 'Green';

SELECT * FROM person WHERE favorite_color IN ('Orange', 'Green', 'Blue');

SELECT * FROM person WHERE favorite_color IN ('Yellow', 'Purple');

CREATE TABLE orders (person_id SERIAL, product_name VARCHAR, product_price NUMERIC, quantity INTEGER);

INSERT INTO orders (person_id, product_name, product_price, quantity)
Values (2, 'Ninja', 59.99, 1),
			 (4, 'Insta-Pot', 99.99, 1),
       (1, 'Boots', 109.99, 2),
       (4, 'Tree', 89.99, 4),
       (4, 'Wine', 29.99, 16);

SELECT * FROM orders

SELECT sum(quantity) FROM orders;

SELECT sum(product_price * quantity) FROM orders;

SELECT sum(product_price * quantity) FROM orders WHERE person_id =4;

INSERT INTO artist (name) 
VALUES ('Katy Perry'),
			 ('Lights'),
       ('Scissor Sisters');

SELECT * FROM artist ORDER BY name DESC LIMIT 10;

SELECT * FROM artist ORDER BY name ASC LIMIT 5;

SELECT * FROM artist WHERE name LIKE 'Black%';

SELECT * FROM artist WHERE name LIKE '%Black%';

SELECT first_name last_name FROM employee WHERE city = 'Calgary';

SELECT MAX(birth_date) FROM employee;

SELECT MIN(birth_date) FROM employee;

SELECT * FROM employee WHERE reports_to = 2;

SELECT count(*) FROM employee WHERE city = 'Lethbridge';

SELECT count(*) FROM invoice WHERE billing_country = 'USA';

SELECT MAX(total) FROM invoice;

SELECT MIN(total) FROM invoice;

SELECT * FROM invoice WHERE total > 5;

SELECT * FROM invoice WHERE total < 5;

SELECT count(*) FROM invoice WHERE billing_state IN ('CA', 'TX', 'AZ');

SELECT avg(total) FROM invoice;

SELECT sum(total) FROM invoice;


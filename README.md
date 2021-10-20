# registraciya-na-github-kirinomitake
registraciya-na-github-kirinomitake created by GitHub Classroom

07.09.21

Задание №1
SELECT SUM FROM billing WHERE payer_email = 'vasya@mail.com';


Задание №2
INSERT INTO billing (payer_email, recipient_email, sum, currency, billing_date, comment) 
VALUES ('pasha@mail.com', 'katya@mail.com', '300.00', 'EUR', '14.02.2016', 'Valentines day present)')

Задание №3
UPDATE billing 
SET payer_email = 'alex@mail.com' 
WHERE 'payer_email' = 'igor@mail.com'

Задание №4
DELETE FROM billing
WHERE 'payer_email' = '' OR 'recipient_email' = '';


10.09.21

Задание 5
SELECT COUNT(1) FROM project

Задание 6
SELECT category, COUNT(product_name) FROM store GROUP BY category

Задание 7
SELECT category, SUM(price*sold_num) result FROM store GROUP BY category ORDER BY result DESC LIMIT 5;

Задание 8
SELECT COUNT(project_name), (budget * COUNT(1)), Datediff(project_start, project_finish) FROM project

04.10.21

#1
SELECT good.name, category.name FROM category_has_good
INNER JOIN good ON category_has_good.good_id = good.id
INNER JOIN category ON category_has_good.category_id = category.id
ORDER BY good.name, category.name;

#2
SELECT client.first_name, client.last_name, count(1) AS new_sale_num FROM client
	INNER JOIN sale ON client.id = sale.client_id
    INNER JOIN status ON sale.status_id = status.id WHERE status.name = "new"
    GROUP BY client.first_name, client.last_name;

#3
SELECT good.name, category.name FROM good
LEFT OUTER JOIN category_has_good ON good.id = category_has_good.good_id
lEFT OUTER JOIN category ON category.id = category_has_good.category_id
GROUP BY good.name, category.name;

14.10.21

1) ---------------------------------

SELECT departament.name
FROM departament AS dept
JOIN users ON users.id = dept.id
WHERE d_id is NULL

------------------------------------

2) ---------------------------------

SELECT departament.name
FROM departament AS dept
JOIN users ON users.id = d.id
WHERE COUNT (users.name) > 1

------------------------------------

3) ---------------------------------

SELECT departament.name
FROM departament AS dept
JOIN users ON dept.id = users.d_id
WHERE dept.name is NULL

------------------------------------

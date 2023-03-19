# Домашнее задание к занятию 12.4. «SQL. Часть 2» - Пугач Евгений.


---

## `Задание 1`


### Решение: 

![Скриншот 1](https://github.com/PugachEV72/Images/blob/master/2023-03-19_15-12-51.png)

SELECT s.store_id, st.last_name AS "Фамилия сотрудника", st.first_name AS "Имя сотрудника", ci.city AS "Город нахождения", COUNT(c.customer_id) AS "Кол-во пользователей"  
FROM sakila.store s  
JOIN sakila.customer c ON s.store_id = c.store_id  
JOIN sakila.staff st ON s.manager_staff_id = st.staff_id   
JOIN sakila.address a ON s.address_id = a.address_id  
JOIN sakila.city ci ON a.city_id = ci.city_id  
GROUP BY s.store_id  
HAVING COUNT(c.customer_id) > 300;

---

## `Задание 2`


### Решение:

![Скриншот 2](https://github.com/PugachEV72/Images/blob/master/2023-03-19_15-16-27.png)

SELECT COUNT(f.film_id) AS 'Кол-во фильмов'  
FROM sakila.film f  
WHERE f.`length` > (SELECT AVG(f.`length`) FROM sakila.film f);

---

## `Задание 3`


### Решение:

![Скриншот 3](https://github.com/PugachEV72/Images/blob/master/2023-03-19_15-25-10.png)

SELECT date_format(p.payment_date, '%M') AS 'Месяц', SUM(p.amount) AS 'Сумма', COUNT(p.rental_id) AS 'Кол-во аренд'  
FROM sakila.payment p  
GROUP BY date_format(p.payment_date, '%M')  
ORDER BY 2 DESC   
LIMIT 1;

---
---

### Дополнительные задания (со звездочкой*)

## `Задание 4`


### Решение:

![Скриншот 4](https://github.com/PugachEV72/Images/blob/master/2023-03-19_15-33-49.png)

---

## `Задание 5`


### Решение:

![Скриншот 5](https://github.com/PugachEV72/Images/blob/master/2023-03-19_15-51-18.png)



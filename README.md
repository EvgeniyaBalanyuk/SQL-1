# Домашнее задание к занятию "`SQL. Часть 1`" - `Баланюк Евгения`

---

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

```
SELECT DISTINCT district 
FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```

![](https://github.com/EvgeniyaBalanyuk/screenshots/blob/main/SQL_1%20№1.png)

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

```
SELECT amount, CAST(payment_date AS DATE)
FROM payment
WHERE payment_date > '2005-06-15 00:00:00' AND payment_date < '2005-06-18 23:59:59'
AND amount > 10.00;
```

![](https://github.com/EvgeniyaBalanyuk/screenshots/blob/main/SQL-1%20№2.png)

### Задание 3

Получите последние пять аренд фильмов.

```
SELECT * 
FROM rental
LIMIT 5
OFFSET 16039;
```

![](https://github.com/EvgeniyaBalanyuk/screenshots/blob/main/SQL_1%20№3.png)

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

```
SELECT LOWER(REPLACE(first_name, 'LL', 'PP')), LOWER(last_name)
FROM customer
WHERE first_name = 'Kelly' OR first_name = 'Willie';
```

![](https://github.com/EvgeniyaBalanyuk/screenshots/blob/main/SQL-1%20№4.png)

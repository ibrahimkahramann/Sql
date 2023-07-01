<br>
<br>


 ![Image](assets/logo.png)

<br>


 # SQL Eğitim Patika 
 

> #### Bu repo'da [Patika](https://academy.patika.dev/) SQL eğitiminde yapmış olduğunuz ödevler bulunmaktadır.

<br>

### Gitmek istediğiniz bölüme tıklayın.

- [**SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal**](#SQL-Ödev-01-WHERE-ve-Karşılaştırma-ve-Mantıksal-Operatörler)
- [**SQL Ödev 02 | BETWEEN ve IN**](#SQL-Ödev-02-BETWEEN-ve-IN)
- [**SQL Ödev 03 | LIKE ve ILIKE**](#SQL-Ödev-03-LIKE-ve-ILIKE)
- [**SQL Ödev 04 | DISTINCT ve COUNT**](#SQL-Ödev-04-DISTINCT-ve-COUNT)
- [**SQL Ödev 05 | ORDER BY | LIMIT ve OFFSET**](#SQL-Ödev-05-ORDER-BY-LIMIT-ve-OFFSET)
- [**SQL Ödev 06 | Aggregate Fonksiyonlar**](#SQL-Ödev-06-Aggregate-Fonksiyonlar)
- [**SQL Ödev 07 | GROUP BY | HAVING**](#SQL-Ödev-07-GROUP-BY-HAVING)
- [**SQL Ödev 08 | Tablo Oluşturmak | Verileri Güncellemek**](#SQL-Ödev-08-Tablo-Oluşturmak-Verileri-Güncellemek)
- [**SQL Ödev 09 | INNER JOIN**](#SQL-Ödev-09-INNER-JOIN)
- [**SQL Ödev 10 | LEFT JOIN, RIGHT JOIN, FULL JOIN**](#SQL-Ödev-10-LEFT-JOIN-RIGHT-JOIN-FULL-JOIN)
- [**SQL Ödev 11 | UNION, INTERSECT ve EXCEPT**](#SQL-Ödev-11-UNION-INTERSECT-EXCEPT)
- [**SQL Ödev 12 | Sorgu Senaryoları**](#SQL-Ödev-12-Sorgu-Senaryoları)

<br>
<br>
<br>


## SQL Ödev 01 WHERE ve Karşılaştırma ve Mantıksal Operatörler 

<br>

1-) <strong>film </strong>tablosunda bulunan <strong>title</strong> ve <strong>description</strong> 
sütunlarındaki verileri sıralayınız.



```sql

SELECT title, description FROM film;

```
![Image](assets/1.1.png)

<br>
<br>
<br>

2-) <strong>film</strong>  tablosunda bulunan tüm sütunlardaki verileri film uzunluğu <strong>(length)</strong>  60 dan büyük <strong>VE</strong>  75 ten küçük olma koşullarıyla sıralayınız.



```sql

SELECT * FROM film
WHERE length > 60 AND length < 75;

```
![Image](assets/1.2.png)


<br>
<br>
<br>

3-)  <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri  <strong>rental_rate</strong> 0.99  <strong>VE</strong>  <strong>replacement_cost</strong> 12.99  <strong>VEYA</strong> 28.99 olma koşullarıyla sıralayınız.



```sql

SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 
OR replacement_cost = 28.99;

```
![Image](assets/1.3.png)


<br>
<br>
<br>

4-) <strong>customer</strong> tablosunda bulunan <strong>first_name</strong> sütunundaki değeri 'Mary' olan müşterinin <strong>last_name</strong> sütunundaki değeri nedir?



```sql

SELECT last_name FROM customer
WHERE first_name = 'Mary';

```
![Image](assets/1.4.png)


<br>
<br>
<br>

5-) <strong>film</strong>  tablosundaki <strong>uzunluğu(length)</strong>  50 ten büyük OLMAYIP aynı zamanda <strong>rental_rate</strong>  değeri 2.99 <strong>veya</strong>  4.99 OLMAYAN verileri sıralayınız.

```sql

SELECT * FROM film
WHERE length <= 50 
AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);

```
![Image](assets/1.5.png)

<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>


## SQL Ödev 02 BETWEEN ve IN

<br>

1-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri <strong>replacement cost</strong> değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```sql

SELECT * FROM film 
WHERE replacement_cost BETWEEN 12.99 AND 16.99;

```
![Image](assets/2.1.png)

<br> 
<br>
<br>

2-) <strong>actor</strong> tablosunda bulunan <strong>first_name</strong> ve <strong>last_name</strong> sütunlardaki verileri <strong>first_name</strong> 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```sql

SELECT first_name, last_name FROM actor 
WHERE first_name IN ('Penelope', 'Nick', 'Ed');

```
![Image](assets/2.2.png)

<br>
<br>
<br>

3-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri <strong>rental_rate</strong> 0.99, 2.99, 4.99 VE <strong>replacement_cost</strong> 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```sql

SELECT * FROM film
WHERE rental_rate IN (0.99, 2.99, 4,99) AND replacement_cost IN (12.99, 15.99, 29.99);
```
![Image](assets/2.3.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 03 LIKE ve ILIKE

<br>

1-)  <strong>country</strong> tablosunda bulunan  <strong>country</strong> sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```sql

SELECT country FROM country
WHERE country LIKE 'A%a' 

```
![Image](assets/3.1.png)


<br>
<br>
<br>

2-) <strong>country</strong> tablosunda bulunan <strong>country</strong> sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```sql
SELECT country FROM country 
WHERE country LIKE '_____%n' 
```
![Image](assets/3.2.png)

<br>
<br>
<br>

3-) <strong>film</strong> tablosunda bulunan <strong>title</strong> sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin <strong>'T'</strong> karakteri içeren film isimlerini sıralayınız.

```sql
SELECT title FROM film 
WHERE title ~~* '%T%T%T%T%' 
```
![Image](assets/3.3.png)

<br>
<br>
<br>

4-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verilerden <strong>title</strong> 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve <strong>rental_rate</strong> 2.99 olan verileri sıralayınız.

```sql
SELECT * FROM film 
WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99; 
```
![Image](assets/3.4.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 04 DISTINCT ve COUNT

<br>

1-)  <strong>film</strong> tablosunda bulunan  <strong>replacement_cost</strong> sütununda bulunan birbirinden farklı değerleri sıralayınız.

```sql

SELECT DISTINCT replacement_cost FROM film

```
![Image](assets/4.1.png)

<br>
<br>
<br>

2-) <strong>film</strong> tablosunda bulunan <Strong>replacement_cost</strong> sütununda birbirinden farklı kaç tane veri vardır?

```sql

SELECT COUNT (DISTINCT replacement_cost) FROM film

```
![Image](assets/4.2.png)

<br>
<br>
<br>

3-) <strong>film</strong> tablosunda bulunan film isimlerinde  <strong>(title)</strong> kaç tanesini T karakteri ile başlar ve aynı zamanda  <strong>rating</strong> 'G' ye eşittir?

```sql

SELECT COUNT(*) FROM film 
WHERE title LIKE 'T%' AND rating = 'G';

```
![Image](assets/4.3.png)
<br>
<br>
<br>



4-) <strong>country</strong> tablosunda bulunan ülke isimlerinden (country) kaç tanesi <strong>5</strong> karakterden oluşmaktadır?


```sql

SELECT COUNT(DISTINCT country) FROM country
WHERE country LIKE '_____';

```
![Image](assets/4.4.png)

<br>
<br>
<br>

5-) city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

```sql

SELECT COUNT(DISTINCT city) FROM city
WHERE city ILIKE '%r';

```
![Image](assets/4.4.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 05 ORDER BY LIMIT ve OFFSET

<br>

1-) film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```sql
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```
![Image](assets/5.1.png)
<br>
<br>
<br>

2-) film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.


```sql
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;
```
![Image](assets/5.2.png)
<br>
<br>
<br>

3-) customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.


```sql
SELECT *
FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```
![Image](assets/5.3.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 06 Aggregate Fonksiyonlar

<br>

1-) film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?


```sql
SELECT ROUND(AVG(rental_rate),3) 
FROM film ;
```
![Image](assets/6.1.png)


<br>
<br>
<br>

2-) film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```sql
SELECT COUNT(*)
FROM film
WHERE title LIKE 'C%';
```
![Image](assets/6.2.png)
<br>
<br>
<br>

3-) film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```sql
SELECT MAX(length) 
FROM film 
WHERE rental_rate = 0.99;
```
![Image](assets/6.3.png)
<br>
<br>
<br>

4-) film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?


```sql
SELECT COUNT(DISTINCT replacement_cost) 
FROM film 
WHERE length > 150;
```
![Image](assets/6.4.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 07 GROUP BY HAVING

<br>

1-) film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.


```sql
SELECT rating, COUNT(*) FROM film
GROUP BY rating;
```
![Image](assets/7.1.png)

<br>
<br>
<br>

2-) film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

```sql
SELECT replacement_cost, COUNT(*)
FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50
```
![Image](assets/7.2.png)
<br>
<br>
<br>

3-) customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

```sql
SELECT store_id, COUNT(*) 
FROM customer
GROUP BY store_id;
```
![Image](assets/7.3.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

 4-) city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

 ```sql
SELECT country_id, COUNT(*) 
FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;
```
![Image](assets/7.4.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 08 Tablo Oluşturmak Verileri Güncellemek"

<br>

1-) test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.


```sql
CREATE TABLE employee (
  id INTEGER,
  name VARCHAR(50) NOT NULL,
  birthday DATE,
  email VARCHAR(100)
);
```
![Image](assets/8.1.png)

<br>
<br>
<br>

2-) Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```sql
insert into employee (name, birthday, email) values ('Julianne', '2008-05-20', 'jduker0@yelp.com');
insert into employee (name, birthday, email) values ('Nolie', '2022-04-03', 'ndaniell1@tripod.com');
```
![Image](assets/8.2.png)
<br>
<br>
<br>

3-) Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.


```sql
-- İsim (name) sütununu güncellemek:

UPDATE employee
SET name = 'John Doe'
WHERE name = 'Cullan'
RETURNING *;
```
![Image](assets/8.3.png)

```sql
-- Doğum günü (birthday) sütununu güncellemek:

UPDATE employee
SET birthday = '1990-06-15'
WHERE email = 'yserckd@home.pl';


-- E-posta (email) sütununu güncellemek:

UPDATE employee
SET email = 'johndoe@example.com'
WHERE birthday = '1950/04/10';


-- İsim ve doğum günü sütunlarını güncellemek:

UPDATE employee
SET name = 'Jane Smith',
    birthday = '1985-03-20'
WHERE id = 4;


-- Tüm sütunları güncellemek:

UPDATE employee
SET name = 'Robert Johnson',
    birthday = '1978-12-10',
    email = 'robertjohnson@example.com'
WHERE id = 5;
```


<br>
<br>
<br>


4-) Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.



```sql
DELETE FROM employee
WHERE id = 44
RETURNING *;
```
![Image](assets/8.4.png)

```sql
DELETE FROM employee
WHERE name ='Constantin';

DELETE FROM employee
WHERE name = 'Jane Smith' AND birthday = '1985-03-20';

DELETE FROM employee
WHERE email = 'umallinsonn@hp.com';

DELETE FROM employee
WHERE id >5
RETURNING *;
```
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 09 INNER JOIN

<br>

1-) city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```sql
SELECT city, country
FROM city
INNER JOIN country ON city.country_id = country.country_id;
```
![Image](assets/9.1.png)

<br>
<br>
<br>

2-) customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.


```sql
SELECT payment_id, first_name, last_name FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id;
```
![Image](assets/9.2.png)

<br>
<br>
<br>

3-) customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.


```sql
SELECT rental_id, first_name, last_name FROM customer
INNER JOIN rental ON customer.customer_id = rental.customer_id;
```
![Image](assets/9.3.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)



<br>
<br>
<br>

## SQL Ödev 10 LEFT JOIN RIGHT JOIN FULL JOIN

<br>
1-) city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.



```sql
SELECT city.city, country.country
FROM city
LEFT JOIN country ON city.country_id = country.country_id;
```
![Image](assets/10.1.png)

<br>
<br>
<br>

2-) customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.



```sql
SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
```
![Image](assets/10.2.png)

<br>
<br>
<br>

3-) customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.



```sql
SELECT rental_id, first_name, last_name FROM customer
FULL JOIN rental ON customer.customer_id= rental.customer_id;
```
![Image](assets/10.3.png)
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 11 UNION INTERSECT EXCEPT

1-) actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.


```sql
SELECT first_name 
FROM actor
UNION 
SELECT first_name
FROM customer;
```
![Image](assets/11.1.png)
<br>
<br>
<br>

2-) actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.


```sql
SELECT first_name 
FROM actor
INTERSECT
SELECT first_name
FROM customer;
```
![Image](assets/11.2.png)

<br>
<br>
<br>

3-) actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.


```sql
SELECT first_name 
FROM actor 
EXCEPT 
SELECT first_name 
FROM customer;
```
![Image](assets/11.3.png)

<br>
<br>
<br>

4-) İlk 3 sorguyu tekrar eden veriler için de yapalım.


```sql
SELECT first_name 
FROM actor
UNION ALL
SELECT first_name
FROM customer;
```
![Image](assets/11.4.png)
```sql
SELECT first_name 
FROM actor
INTERSECT ALL
SELECT first_name
FROM customer;


SELECT first_name 
FROM actor 
EXCEPT ALL
SELECT first_name 
FROM customer;
```
<br>

[Başa Dön](#SQL-Eğitim-Patika)

<br>
<br>
<br>

## SQL Ödev 12 Sorgu Senaryoları

1-) film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?


```sql
SELECT COUNT(*)
FROM film
WHERE length > (
  SELECT AVG(length)
  FROM film
);
```
![Image](assets/12.1.png)

<br>
<br>
<br>

2-) film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

```sql
SELECT COUNT(*)
FROM film
WHERE rental_rate = (
  SELECT MAX(rental_rate)
  FROM film
);
```
![Image](assets/12.2.png)

<br>
<br>
<br>

3-) film tablosunda en düşük rental_rate ve en düşük replacement_cost değerlerine sahip filmleri sıralayınız.


```sql
SELECT * FROM film
WHERE rental_rate = (
  SELECT MIN(rental_rate)
  FROM film
)
AND replacement_cost = (
  SELECT MIN(replacement_cost)
  FROM film
);
```
![Image](assets/12.3.png)

<br>
<br>
<br>

4-) payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.


```sql
SELECT customer_id, COUNT(*) AS transaction_count
FROM payment
GROUP BY customer_id
ORDER BY transaction_count DESC;
```
![Image](assets/12.4.png)
<br>
<br>
<br>
<hr>
<br>

Bu repo'da [Patika](https://academy.patika.dev/) SQL eğitimindeki ödevler vardır. İçerisinde bir adet README dosyası barındırıyor.


## Installation

Öncelikle projeyi clonelayın.

```
https://github.com/ibrahimkahramann/sql.git
```

## Usage

Projeyi cloneladıktan sonra Visual Studio Code programında açınız.

Linux için:

```
cd sql
code .
```

## Contributing
Pull requestler kabul edilir. Büyük değişiklikler için, lütfen önce neyi değiştirmek istediğinizi tartışmak için bir konu açınız.

## License
[MIT](https://choosealicense.com/licenses/mit/)

<br>

<hr>

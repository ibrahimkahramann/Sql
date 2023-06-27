<br>
<br>


 ![Image](assets/logo.png)

<br>


 # SQL Eğitim Patika 

> #### Bu repo'da [Patika](https://academy.patika.dev/) SQL eğitiminde yapmış olduğunuz ödevler bulunmaktadır.

<br>

 - **SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal**





<br>


## SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal Operatörler 

<br>
<br>
<br>

1-) <strong>film </strong>tablosunda bulunan <strong>title</strong> ve <strong>description</strong> 
sütunlarındaki verileri sıralayınız.



```sql

SELECT title, description FROM film;

```
![Image](assets\1.1.png)

<br>
<br>
<br>

2-) <strong>film</strong>  tablosunda bulunan tüm sütunlardaki verileri film uzunluğu <strong>(length)</strong>  60 dan büyük <strong>VE</strong>  75 ten küçük olma koşullarıyla sıralayınız.



```sql

SELECT * FROM film
WHERE length > 60 AND length < 75;

```
![Image](assets\1.2.png)


<br>
<br>
<br>

3-)  <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri  <strong>rental_rate</strong> 0.99  <strong>VE</strong>  <strong>replacement_cost</strong> 12.99  <strong>VEYA</strong> 28.99 olma koşullarıyla sıralayınız.



```sql

SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 
OR replacement_cost = 28.99;

```
![Image](assets\1.3.png)


<br>
<br>
<br>

4-) <strong>customer</strong> tablosunda bulunan <strong>first_name</strong> sütunundaki değeri 'Mary' olan müşterinin <strong>last_name</strong> sütunundaki değeri nedir?



```sql

SELECT last_name FROM customer
WHERE first_name = 'Mary';

```
![Image](assets\1.4.png)


<br>
<br>
<br>

5-) <strong>film</strong>  tablosundaki <strong>uzunluğu(length)</strong>  50 ten büyük OLMAYIP aynı zamanda <strong>rental_rate</strong>  değeri 2.99 <strong>veya</strong>  4.99 OLMAYAN verileri sıralayınız.

```sql

SELECT * FROM film
WHERE length <= 50 
AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);

```
![Image](assets\1.5.png)

<br>
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

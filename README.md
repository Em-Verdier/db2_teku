# db2_teku :floppy_disk:

**##Excercice 1**

Télécharger la base de donnée: https://sp.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip
Dézipper le fichier dvdrental.zip et installer la base de donnée dvdrental.tar avec les commandes suivantes:
```
dvdrental=> \dt+
                          List of relations
 Schema |     Name      | Type  |  Owner  |    Size    | Description 
--------+---------------+-------+---------+------------+-------------
 public | actor         | table | db_user | 40 kB      | 
 public | address       | table | db_user | 88 kB      | 
 public | category      | table | db_user | 8192 bytes | 
 public | city          | table | db_user | 64 kB      | 
 public | country       | table | db_user | 8192 bytes | 
 public | customer      | table | db_user | 96 kB      | 
 public | film          | table | db_user | 464 kB     | 
 public | film_actor    | table | db_user | 264 kB     | 
 public | film_category | table | db_user | 72 kB      | 
 public | inventory     | table | db_user | 224 kB     | 
 public | language      | table | db_user | 8192 bytes | 
 public | payment       | table | db_user | 888 kB     | 
 public | rental        | table | db_user | 1224 kB    | 
 public | staff         | table | db_user | 16 kB      | 
 public | store         | table | db_user | 8192 bytes | 
(15 rows)

dvdrental-> \dt+ actor
                   List of relations
 Schema | Name  | Type  |  Owner  | Size  | Description 
--------+-------+-------+---------+-------+-------------
 public | actor | table | db_user | 40 kB | 
(1 row)

```

**##2**

Ecrivez une requête SQL qui affiche tous les titres et descriptions des films dont la description contient le mot Amazing

```
dvdrental=> SELECT title, description  FROM film WHERE description  LIKE '%Amazing%'
;
```

**##3**

Ecrivez une requête SQL qui affiche le chiffre d'affaire gagné par le video club depuis son ouverture.

```
dvdrental=> SELECT customer.first_name, customer.last_name, customer.customer_id, payment.amount, payment_date FROM customer JOIN payment ON customer.customer_id = payment.customer_id WHERE amount>10; 

```

*##3bis*

Ecrivez une requête SQL qui affiche le chiffre d'affaire gagné par le video club depuis son ouverture.

```
dvdrental=> SELECT SUM (amount) AS total FROM payment;
  total   
----------
 61312.04
(1 row)

```

**##4**

Ecrivez une requête SQL qui affiche le titre de tous les films dont la langue est l'anglais et dont la durée est supérieure à 120 minutes.

```
SELECT title FROM film JOIN language ON film.language_id = language.language_id WHERE film.language_id = 1 AND length > 120
```






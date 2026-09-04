# **PostgreSQL Syntax Guide**

* **How to view contents in a table**

In Visual Studio Code:

&#x09;**'cursorobject.execute("""SELECT \* FROM tableName;""")**

&#x09; **print(cursorobject.fetchall())'**



In SQL Shell:

&#x09;**'The\_Odyssey=# SELECT \* FROM tableName;**

&#x09;

**- View Specfic Columns**

&#x09;In Visual Studio Code:

&#x09;'**cursorWand.execute("""SELECT name FROM fromvscode;""")**

&#x09; **print(cursorWand.fetchall())'**

&#x09;In SQL Shell:

&#x09;**'The\_Odyssey=# SELECT vampire FROM fromSQLShell;'**

&#x09;



* **How to create a 'Table' (Basically the 'contents' of the database)**

In Visual Studio Code:

&#x09;**'cursorobject.execute("""CREATE TABLE fromVSCODE (**

&#x20;   		**Name VARCHAR(255),**

&#x20;   		**Age INT,**

&#x20;   		**Species VARCHAR(255)**

&#x09;**);""")'**



In SQL Shell:

First, type **'CREATE TABLE fromSQLShell ('** then hit enter.

It should now look like this: **'postgres(#'** write the rest of the function per line.

**'The\_Odyssey=# CREATE TABLE fromSQLShell (**

&#x20;**The\_Odyssey(# Vampire VARCHAR(255),**

&#x20;**The\_Odyssey(# VampireAge INT**

&#x20;**The\_Odyssey(# );'**

It will then print 'CREATE TABLE' if successful.



* **How to insert contents into a table**

In Visual Studio Code:

&#x09;**'cursorWand.execute("""INSERT INTO fromvscode (name)**

&#x09; **VALUES ('Luna');**

&#x09; **""")'**



In SQL Shell:

&#x09;**'INSERT INTO fromSQLShell (vampire, vampireage) VALUES ('Dracula', 470);'**



* **How to add a column**

In Visual Studio Code:

&#x09;'**cursorWand.execute("""ALTER TABLE fromvscode**

&#x09;**ADD Kills VARCHAR(255);**

&#x09;**""")'**



In SQL Shell:

&#x09;**'ALTER TABLE fromSQLShell ADD dateturned VARCHAR(255);'**



* **How to update a value**

In Visual Studio Code:

&#x09;'**cursorWand.execute("""UPDATE fromvscode**

&#x09;**SET name = 'The Indoraptor'**

&#x09;**WHERE name = 'Luna';**

&#x09;**""")'**



In SQL Shell:

&#x09;**'UPDATE fromSQLShell SET vampireage = 471 WHERE vampire = 'Dracula';'**



* **How to update a column value type:**

In Visual Studio Code:

&#x09;'**cursorWand.execute("""ALTER TABLE fromvscode**

&#x09;**ALTER COLUMN kills TYPE VARCHAR(255);**

&#x09;**""")'**



In SQL Shell:

&#x09;**'ALTER TABLE fromSQLShell ALTER COLUMN dateturned TYPE VARCHAR(255);'**



* **How to remove a column:**

In Visual Studio Code:

&#x09;**'cursorWand.execute("""ALTER TABLE fromvscode**

&#x09;**DROP COLUMN kills;**

&#x09;**""")'**



In SQL Shell:

&#x09;**'ALTER TABLE fromSQLShell DROP COLUMN dateturned;'**



* **How to delete a row from a table:**

In Visual Studio Code:

&#x09;'**cursorWand.execute("""DELETE FROM fromvscode**

&#x09;**WHERE name = 'The Indoraptor';**

&#x09;**""")'**



In SQL Shell:

&#x09;**'DELETE FROM fromSQLShell WHERE vampireage = 1500;'**



**'DELETE FROM fromvscode'** Deletes everything IN the table. **'DROP TABLE fromvscode'** Deletes THE table.



### Part 2: More

(Everything shown below can be applied to either Visual Studio Code or SQL Shell, we have been occasionally running it in both)

* **Operators**

=	Equal to

<	Less than

>	Greater than

<=	Less than or equal to

>=	Greater than or equal to

<>	Not equal to

!=	Not equal to

LIKE	Check if a value matches a pattern (case sensitive)

ILIKE	Check if a value matches a pattern (case insensitive)

AND	Logical AND

OR	Logical OR

IN	Check if a value matches any value within a provided list

BETWEEN	Check if a value is within a specified range

IS NULL	Check if a value is NULL

NOT	Makes a negative result e.g. NOT LIKE, NOT IN, NOT BETWEEN



Examples:

**SELECT \* FROM fromvscode WHERE vampire\_age < 1000;**

**SELECT name FROM fromSQLShell WHERE name NOT LIKE 'H%';**



* **Selections**

For more specific selections, **SELECT name,speability,kills FROM fromSQLShell;** 'name' 'speability' and 'kills' are three separate categories.



In case you have duplicate values in your database, you can use: **SELECT DISTINCT name FROM fromSQLShell;** Using **SELECT COUNT(DISTINCT name) FROM fromSQLShell;** Counts the total different values



* **Where**

Basically from the Operators, **SELECT \* FROM fromvscode WHERE vampire\_name = 'Reacher';**



* **Ordering**

With integer value (lowest to highest) = **SELECT \* FROM fromvscode ORDER BY vampire\_age;** To order it (highest to lowest): **SELECT \* FROM fromvscode ORDER BY vampire\_age DESC;**

With Alphabetically = **SELECT name FROM fromSQLShell ORDER BY name;** And yes, you can even do: **SELECT DISTINCT name FROM fromSQLShell ORDER BY name;**



* **Limit**

To retrieve a maximum amount (like 3) = **SELECT \* FROM fromSQlShell LIMIT 3;** And for a 'range\*\*': SELECT \* FROM fromSQLShell LIMIT 5 OFFSET 2;\*\*



* **MIN and MAX**

Min: **SELECT MIN(age) FROM fromSQLShell;**

Max: **SELECT MAX(vampire\_age) FROM fromvscode;**

Extra detail, this will set the column name provided to something you want: **SELECT MAX(vampire\_age) AS Youngest\_Vampire FROM fromvscode;** (Seems to only work in SQL Shell)



* **Counting Specifics**

Counting how many of, (like how many vampires are older than 100?): **SELECT COUNT(vampire\_age) FROM fromvscode WHERE vampire\_age > 100;**



* **Sum**

Everything added up from a column (Numbers only): **SELECT SUM(age) FROM fromSQLShell;**



* **Averaging**

General Averaging: **SELECT AVG(age)::NUMERIC(10,2) FROM fromSQLShell;**

With '2' Decimals: (This was just the example shown) **SELECT AVG(age)::NUMERIC(10,2) FROM fromSQLShell;**



* **Like**

Entries that HAVE something, (like the letter 'R' in this example): **SELECT \* FROM fromvscode WHERE vampire\_name LIKE '%R%';**

Entries that START with something (like the letter 'L'): **SELECT \* FROM fromSQLShell WHERE name LIKE 'L%';**

Entries that have either the upper or lowercase letter: **SELECT \* FROM fromSQLShell WHERE name ILIKE '%r%';**

Entries that END with something: **SELECT \* FROM fromSQLShell WHERE name LIKE '%a';**

Entries that have something oddly specific: **SELECT \* FROM fromSQLShell WHERE name LIKE 'H\_gh';**



* **In**

Entries in a specific category (Entries where the speability is equal to 'The Empress'): **SELECT \* FROM fromSQLShell WHERE speability IN ('The Empress');** (There is also a 'NOT IN')

There is this, but idk what it really is: **SELECT \* FROM customers WHERE customer\_id IN (SELECT customer\_id FROM orders);** (There is a 'NOT IN' aswell)



* **Between**

This can work with numbers or text: 

Numbers: **SELECT \* FROM fromvscode WHERE vampire\_age BETWEEN 100 AND 4000;**

Text: **SELECT \* FROM fromSQLShell WHERE speability BETWEEN 'Bat\_Swarm' AND 'Echo\_Eyes';**

Date: **SELECT \* FROM orders WHERE order\_date BETWEEN '2023-04-12' AND '2023-05-05';**



* **Join**

This, doesn't really seem to work for my databases: **SELECT vampire\_name FROM fromvscode INNER JOIN fromSQLShell ON fromvscode.kills = fromSQLShell.kills;**

Left Join: **SELECT vampire\_name FROM fromvscode LEFT JOIN fromSQLShell ON fromvscode.kills = fromSQLShell.kills;**

Right Join:  **SELECT vampire\_name FROM fromvscode RIGHT JOIN fromSQLShell ON fromvscode.kills = fromSQLShell.kills;**

Full Join:  **SELECT vampire\_name FROM fromvscode FULL JOIN fromSQLShell ON fromvscode.kills = fromSQLShell.kills;**

Cross Join:  **SELECT vampire\_name FROM fromvscode CROSS JOIN fromSQLShell;**

(Bro what is half of this stuff doing)



* **Union**

Combine two sets of tables: **SELECT vampire\_name, kills FROM fromvscode UNION SELECT name, kills FROM fromSQLShell;**



* **Case**

Basically like Case statements in Python: **SELECT vampire\_name, kills, CASE WHEN kills > 1000 THEN 'RED ALERT' WHEN kills < 1000 THEN 'YELLOW ALERT' ELSE 'UNKNOWN' END FROM fromvscode;**




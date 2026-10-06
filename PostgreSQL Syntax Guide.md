# **PostgreSQL Syntax Guide** 

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Viewing]**



**{How to view contents in a table}**



**<In SQL Shell>**



The\_Odyssey=# SELECT \* FROM tableName;



**<In Visual Studio Code>**



cursorobject.execute("""SELECT \* FROM tableName;""")



print(cursorobject.fetchall())

&#x09;

**{View Specfic Columns}**



**<In SQL Shell>**



The\_Odyssey=# SELECT vampire FROM fromSQLShell;



**<In Visual Studio Code>**



cursorWand.execute("""SELECT name FROM fromvscode;""")



print(cursorWand.fetchall())

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Tables]**

&#x09;

**{Create a Table}**



**<In SQL Shell>**



(First, type CREATE TABLE fromSQLShell **(** then hit enter. It should now look like this: **'**fromSQLShell**(**#' write the rest of the function per line.)



&#x20;fromSQLShell=# CREATE TABLE fromSQLShell (

&#x20;fromSQLShell(# Vampire VARCHAR(255),

&#x20;fromSQLShell(# VampireAge INT

&#x20;fromSQLShell(# );



(It will then print 'CREATE TABLE' if successful)



**<In Visual Studio Code>**



cursorobject.execute("""CREATE TABLE fromVSCODE (

&#x20;   		Name VARCHAR(255),

&#x20;   		Age INT,

&#x20;   		Species VARCHAR(255)

);""")



**{Insert Content}**



**<In SQL Shell>**



INSERT INTO fromSQLShell (vampire, vampireage) VALUES ('Dracula', 470);



**<In Visual Studio Code>**



cursorWand.execute("""INSERT INTO fromvscode (name)

VALUES ('Luna');

""")



**{Update Values}**



**<In SQL Shell>**

&#x09;

UPDATE fromSQLShell SET vampireage = 471 WHERE vampire = 'Dracula';



**<In Visual Studio Code>**



cursorWand.execute("""UPDATE fromvscode

SET name = 'The Indoraptor'

WHERE name = 'Luna';

""")



**\[Columns]**



**{Add a column}**



**<In SQL Shell>**

&#x09;

ALTER TABLE fromSQLShell ADD dateturned VARCHAR(255);



**<In Visual Studio Code>**



cursorWand.execute("""ALTER TABLE fromvscode

ADD Kills VARCHAR(255);

""")



**{Update a column type}**



**<In SQL Shell>**



ALTER TABLE fromSQLShell ALTER COLUMN dateturned TYPE VARCHAR(255);



**<In Visual Studio Code>**



cursorWand.execute("""ALTER TABLE fromvscode

ALTER COLUMN kills TYPE VARCHAR(255);

""")



**{Remove a column}**



**<In SQL Shell>**



ALTER TABLE fromSQLShell DROP COLUMN dateturned;



**<In Visual Studio Code>**



cursorWand.execute("""ALTER TABLE fromvscode

DROP COLUMN kills;

""")



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Deleting]**



**{Delete a row}**



**<In SQL Shell>**



DELETE FROM fromSQLShell WHERE vampireage = 1500;



**<In Visual Studio Code>**



cursorWand.execute("""DELETE FROM fromvscode

WHERE name = 'The Indoraptor';

""")



**{Delete table CONTENT}**



**<In SQL Shell>**



DELETE FROM fromvscode



**<In Visual Studio Code>**



cursorWand.execute("""DELETE FROM fromvscode""")



**{Delete the TABLE}**



**<In SQL Shell>**



DROP TABLE fromvscode



**<In Visual Studio Code>**



cursorWand.execute("""DROP TABLE fromvscode""")



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



\[**Operators]**

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



**{Examples}**



SELECT \* FROM fromvscode WHERE vampire\_age < 1000;



SELECT name FROM fromSQLShell WHERE name NOT LIKE 'H%';



**\[Selections]**



(For more specific selections, 'name' 'speability' and 'kills' are three separate categories)



SELECT name,speability,kills FROM fromSQLShell; 



**{Duplicate Values}**



(In case you have duplicate values in your database, you can use)



SELECT DISTINCT name FROM fromSQLShell; 



(The command below, counts the total different values)



SELECT COUNT(DISTINCT name) FROM fromSQLShell; 



**\[Where]**



SELECT \* FROM fromvscode WHERE vampire\_name = 'Reacher';



**\[Ordering]**



(With integer value (lowest to highest) 



SELECT \* FROM fromvscode ORDER BY vampire\_age; 



(To order it (highest to lowest)



&#x20;SELECT \* FROM fromvscode ORDER BY vampire\_age DESC;



(Alphabetically)



SELECT name FROM fromSQLShell ORDER BY name; 



(You can even do) 



SELECT DISTINCT name FROM fromSQLShell ORDER BY name;



**\[Limit]**



(To retrieve a maximum amount (like 3) 



SELECT \* FROM fromSQlShell LIMIT 3; 



(And for a 'range') 



SELECT \* FROM fromSQLShell LIMIT 5 OFFSET 2;\*\*



**\[MIN and MAX]**



**{Min}**



SELECT MIN(age) FROM fromSQLShell;



**{Max}**



SELECT MAX(vampire\_age) FROM fromvscode;



**\[Extra Fact]**



(This will set the column name provided to something you want when display, Seems to only work in SQL Shell)



**SELECT MAX(vampire\_age) AS Youngest\_Vampire FROM fromvscode;** 



**\[Counting Specfics]**



(Counting how many vampires are older than 100?)



SELECT COUNT(vampire\_age) FROM fromvscode WHERE vampire\_age > 100;



**\[Sum]**



(Everything added up from a column (Numbers only)



**SELECT SUM(age) FROM fromSQLShell;**



**\[Averaging]**



(General Averaging)



SELECT AVG(age)::NUMERIC(10,2) FROM fromSQLShell;



(With '2' Decimals: (This was just the example shown)(



SELECT AVG(age)::NUMERIC(10,2) FROM fromSQLShell;



**\[Like]**



**{Entries that contain something}**



SELECT \* FROM fromvscode WHERE vampire\_name LIKE '%R%';



**{Entries that start with something}**



SELECT \* FROM fromSQLShell WHERE name LIKE 'L%';



**{Entries that contain a upper or lowercase letter}**



SELECT \* FROM fromSQLShell WHERE name ILIKE '%r%';



**{Entries that end with something}**



SELECT \* FROM fromSQLShell WHERE name LIKE '%a';



**{Entries that have something oddly specific}** 



SELECT \* FROM fromSQLShell WHERE name LIKE 'H\_gh';



**\[In]**



Entries in a specific category (Entries where the speability is equal to 'The Empress')

&#x20;

SELECT \* FROM fromSQLShell WHERE speability IN ('The Empress'); 



(There is this, but idk what it really is) 



SELECT \* FROM customers WHERE customer\_id IN (SELECT customer\_id FROM orders); 



(There is a 'NOT IN' aswell)



**\[Between]**



(This can work with numbers or text)



SELECT \* FROM fromvscode WHERE vampire\_age BETWEEN 100 AND 4000;



SELECT \* FROM fromSQLShell WHERE speability BETWEEN 'Bat\_Swarm' AND 'Echo\_Eyes';



SELECT \* FROM orders WHERE order\_date BETWEEN '2023-04-12' AND '2023-05-05';



**\[Union]**



(Combine two sets of tables)



SELECT vampire\_name, kills FROM fromvscode UNION SELECT name, kills FROM fromSQLShell;



**\[Case]**



(Basically like Case statements in Python)



SELECT vampire\_name, kills, CASE WHEN kills > 1000 THEN 'RED ALERT' WHEN kills < 1000 THEN 'YELLOW ALERT' ELSE 'UNKNOWN' END FROM fromvscode;


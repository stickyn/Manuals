# **SQL Syntax:**

\*NOTE: This is all default SQL Syntax, although some things can only work with different versions (Like PostgreSQL has different query for modifying datatypes)



**\[Create a Database]**



CREATE DATABASE databasename;

(In PostgreSQL, 'CREATE DATABASE' would be lowercase)



**\[Delete Database]**



DROP DATABASE microsoftDatabase;

**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Create a Table]**



CREATE TABLE tableName (

&#x20;   column1 VARCHAR(255),

&#x20;   column2 VARCHAR(255),

&#x20;   column3 int



);

(You may notice that the 'int' is lowercased, in PostgreSQL, you can use 'INT' or 'int')



**{Create Table from existing table \[Useable in PostgreSQL]}**



CREATE TABLE Halloween\_2026 AS SELECT \* FROM Halloween;



**{Drop Table}**



DROP TABLE table2;



**{Creating backups}**



SELECT \* INTO backupTable4 FROM table4;



SELECT Vampires INTO backupTable4 FROM table4; (You can do with any columns you want)

**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Content of Tables]**



**{Insert content into Tables}**



INSERT INTO table4 VALUES ('Dracula','Skeleton Guy',450);



**{Insert data into specfic columns}**



INSERT INTO table4 (Vampires) VALUES ('Remmick');



**{Insert numerous rows}**



INSERT INTO table4 VALUES ('Dracula','Skeleton Guy',450), ('Dracula','Skeleton Guy',450),('Dracula','Skeleton Guy',450);



**{Update content} (This is very diverse btw)**



UPDATE table4 SET Vampires = 'Basit', Skeletons = 'Barkenstein',Frankensteins = 92 WHERE Vampires = 'Remmick';



(Update multiple rows)

UPDATE table4 SET Skeletons = 'Nighty' WHERE Frankensteins <= 40;



**{Deleting from tables}**



DELETE FROM table4 WHERE Skeletons = 'Skeleton Guy';



**{Copy CONTENT from one table to another}**



(The amount of content you are copying from one table to another must be the same amount)



(First, create a table:)



CREATE TABLE another (

humans VARCHAR(255),

bones VARCHAR(255),

Wolfensteins INT

);



(Then, to copy everything)



INSERT INTO another SELECT \* FROM table4; (table4 has corresponding columns)



(Then, we can create another table)



CREATE TABLE bro (

Nerdy VARCHAR(255)

);



(Finally, we can insert just one column)



INSERT INTO bro SELECT Vampires FROM table4;

**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Viewing Tables]**



**{View everything in a table}**



SELECT \* FROM table4;



**{View specific columns}**



SELECT Vampires, Frankensteins FROM table4;



**{View specific columns with conditions}**



SELECT Vampires, Frankensteins FROM table4 WHERE Frankensteins < 1000;



**{View columns without duplicates}**



SELECT DISTINCT Frankensteins FROM table4 WHERE Frankensteins < 1000;



**\[Table viewing conditions]**



**{Order}**



SELECT \* FROM table4 ORDER BY Frankensteins; (Lowest to highest)



SELECT \* FROM table4 ORDER BY Frankensteins DESC; (Highest to Lowest)



(Including Alphabetically)



SELECT DISTINCT Vampires FROM table4 ORDER BY Vampires;



SELECT \* FROM table4 ORDER BY Vampires, Skeletons; (Order by several columns)



**{And}**



SELECT \* FROM table4 WHERE Vampires = 'Jeffery' AND Frankensteins > 20; \*\*(\*\*Uses multiple conditons)



**{Or}**



SELECT \* FROM table4 WHERE Vampires = 'Jeffery' OR Frankensteins > 20; (Similar just different word}



**{Not}**



SELECT Vampires FROM table4 WHERE NOT Vampires = 'Jeffery';



**{Like}**



SELECT Vampires FROM table4 WHERE Vampires LIKE '%a%'; (Gets everything with an 'a')



SELECT Vampires FROM table4 WHERE Vampires LIKE 'a%'; (Gets everything that starts with an 'a')



SELECT \* FROM table4 WHERE Vampires LIKE '%es%'; (Gets everything that has a 'es' in it)



**{Top}**



SELECT TOP 2 \* FROM table4; (Gets the top 2 selection)



(There is also this 'PERCENT' one)



SELECT TOP 2 PERCENT \* FROM table4;



**{In}**



SELECT \* FROM table4 WHERE Skeletons IN ('Luna'); (Gets all where this value is true)



SELECT \* FROM table4 WHERE Skeletons NOT IN ('Luna'); (Gets all where this value is true)



**{Between}**



SELECT \* FROM table4 WHERE Frankensteins BETWEEN 30 AND 500;



SELECT \* FROM table4 WHERE Frankensteins NOT BETWEEN 30 AND 500;



SELECT \* FROM table4 WHERE Vampires BETWEEN 'a' AND 'e'; (And with words!)



**{Aliases}**



SELECT Vampires AS Infectected\_Vampires, Frankensteins AS Frankenstein\_Monsters FROM table4; (For organization)



(Concatenation)



SELECT Vampires, Vampires + Skeletons AS 'The Monsters' FROM table4; (Some dohickeing)

**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Joins]**



(Tables must have a corresponding column, and we will need to find the right time to use these)



**{Inner Join}**



SELECT \* FROM table4 INNER JOIN table5 ON table4.Frankensteins = table5.Frankensteins;



**{Left Join}**



SELECT table4.Vampires, table5.Frankensteins FROM table4 LEFT JOIN table5 ON table4.Frankensteins = table5.Frankensteins;



**{Right Join}**



SELECT table4.Vampires, table5.Frankensteins FROM table4 RIGHT JOIN table5 ON table4.Frankensteins = table5.Frankensteins;



**{Full Join}**



SELECT table4.Vampires, table5.Frankensteins FROM table4 FULL JOIN table5 ON table4.Frankensteins = table5.Frankensteins;



**{Self Join}**



SELECT A.Vampires AS "Deadpires", B.Vampires AS "Lifepiers" FROM table4 A, table4 B;



**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**





**\[Removal of Tables]**



DROP TABLE Halloween\_2026;

DROP TABLE IF EXISTS Halloween\_2026; (This is a best practice)



**{Truncate Table}**



TRUNCATE TABLE Halloween; (Used to delete **records** in the table but not the table itself)



**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Editing Tables]**



ALTER TABLE tablename; (This is the basic syntax)



**{Adding a column}**



ALTER TABLE Halloween ADD pumpkin\_ediable VARCHAR(255);



**{Removing a column}**



ALTER TABLE Halloween DROP COLUMN pumpkin\_ediable;



**{Renaming a column}**



ALTER TABLE Halloween RENAME COLUMN date to halloween\_night;

(In SQL Server)

EXEC sp\_rename 'table2.Indoraptors', 'Vampires', 'COLUMN';





**{Modifying Datatype}**



(In SQL Server)

ALTER TABLE table2 ALTER COLUMN Vampires VARCHAR(255) NOT NULL;



**{Add a constraint}**



ALTER TABLE Halloween ADD CONSTRAINT CHK\_Age CHECK (store = 'death');



**{Rename Table \[Useable in PostgreSQL}**



ALTER TABLE Halloween RENAME TO Halloween\_Night;



**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Constraints]**



NOT NULL = A column will not accept empty values

UNIQUE = Ensure that all values in a column are unique

PRIMARY KEY = Ensure unique and not non values, and a table can have only ONE at a time

FOREIGN KEY = Link between two tables, and prevents destruction between them

CHECK = Makes sure that values in that column are a certain value (used like an if statement)

DEFAULT = Puts a default value if no other is specified

CREATE INDEX = Create indexes on tables, to speed up data retrieval



&#x09;CREATE INDEX aIndex

&#x09;ON table2 (Vampires,Reapers,Scarecrows);

**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



**\[Functions]**



**{Min}**



SELECT MIN(Frankensteins) AS lowestNumberOfFranks FROM table4;



**{Max}**



SELECT MAX(Frankensteins) AS highestNumberofRanks FROM table4;



**{Count}**



SELECT COUNT(\*) FROM table4; (Count all the rows in a table)



SELECT COUNT(Vampires) FROM table4; (Count Vampires with non-null values)



**{Sum}**



SELECT SUM(Frankensteins) FROM table4; (Counts up everything)



SELECT SUM(Frankensteins - 13) FROM table4; (You can do this, but I'm not sure if it's 100% accurate)



**{Average}**



SELECT AVG(Frankensteins) FROM table4;



**{Group by}**



SELECT Vampires, AVG(Frankensteins) FROM table4 GROUP BY Vampires;




# **PostgreSQL Developer Journey:**



### *Chapter 1: How to install*

1. Go to 'https://www.postgresql.org/' and click on the grey 'Download' button
2. Under 'Packages and Installers' click the respective operating system
3. Click the small link named 'Download the Installer'
4. You are now at 'https://www.enterprisedb.com/downloads/postgres-postgresql-downloads' Click the respective button for your operating system

In the setup wizard of PostgreSQL, you will have to set a password, remember it.



### *Chapter 1.2: Possible Errors*

Frequently encountered error is: 'problem running post install step installation may not complete correctly'

*How To Fix:*

**Solution 1:** PostgreSQL uses 'Microsoft Visual C++ 2015-2022 Redistributable' x64 or x86 which is generally installed with it, in 'apps' click the 3 dots, and click 'modify' (Try one or the other or both)

**Add-on to Solution 1:** Set the download location in 'Downloads' rather than 'Program Files' (but it's installed there anyways)



The next Error you may encounter is when trying to open it. It takes to long to open...

*How To Fix:*

***Solution 1:*** Let the error happen lol, and then in the Error Window, click 'configure' and change the 'Time' to be longer. Then change the port number to be '5432'



One more error can be getting: '**connection timeout expired.Multiple connection attempts failed'**

**Solution 2:** Open Task Manager, Click the three lines, and click **'Services'**, and the **'Open Services'** and find **'postgresql-x64- 18'** and to the left, click **'Start'**



### Chapter 2: Connecting To A Database!

*Using SQL Shell:*

1. Open SQL Shell, usually listed alongside PostgreSQL in Windows Start Menu
2. When open, it will look like this:

**'Server \[localhost]'**



**2.1.** From here, because we are using a default table, you can keep hitting 'enter' until it shows this:

**'Password for user postgres:'**

(Type the password you created in the Setup Wizard)



If successful, a message will show up that looks like this:

**'psql (18.6)**

**WARNING: Console code page (437) differs from Windows code page (1252)**

&#x20;        **8-bit characters might not work correctly. See psql reference**

&#x20;        **page "Notes for Windows users" for details.**

**Type "help" for help.**



**postgres=#'**



*Using PgAdmin4:*

1. Open PgAdmin4, and you may need to enter a 'master password' once again, remember it
2. Now to connect to a database, under **'> Servers ()'** and click **'> PostgreSQL 15'** and enter the setup wizard password
3. Click **'> Databases'** and right click on **'> database\_name'** and click **'Query Tool'**



*Using Visual Studio Code and Python:*

1. Make sure you have **'pyscopg2'** installed. Type **'pip install psycopg2'** in terminal, then in your script **'import pyscopg2'**
2. Create a variable, and set the content as **'psycopg2.connect(host="localhost",dbname="The\_Odyssey",user="postgres",password="Basit",port=5432)'**
3. Now, create a **'cursor'** make a variable and set the connect as '**cursorobject = variablethathadtheconnect.cursor()'**
4. To test, write **'cursorobject.execute("""SELECT version();""")** and then write **'print(cursorWant.fetchall())'**

**5.** Lastly, write **'variablethathadtheconnect.commit(), variablethathadtheconnect.close()'** and 	then **'cursorobject.close()'**

If successful, it should print: **'\[('PostgreSQL 18.6 on x86\_64-windows, compiled by msvc-19.44.35228, 64-bit',)]'**



*Other:*

***Connecting To Other Databases:***

*In SQL Shell:*

In **'Database \[postgres]:'** Type the name of your new database



***Creating Other Databases:***

*In SQL Shell:*

After making a connection with the default database, write: postgres=# **create database databaseName;** It will work if it prints **'CREATE DATABASE'** below



*In PgAdmin4:*

Right Click **'> Databases'** and click **'Create'** and under **'Database'** write your Database's name

**NOTE:** If you are using a name with spaces, you have to use **'\_'** ex: **The\_Odyssey**



### **Open The Cheat sheet for Syntax!**


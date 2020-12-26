Trainer : Raj Prudhvi (Oracle Certified) 
-

Python Database Programming:            
------------------------------
Storage Areas:

* As the Part of our Applications, we required to store our Data like Customers Information, Billing
Information, Calls Information etc..

* To store this Data, we required Storage Areas.

There are 2 types of Storage Areas.

      * Temporary Storage Areas
      * Permanent Storage Areas
    
1.Temporary Storage Areas:
--------------------------------
* These are the Memory Areas where Data will be stored temporarily.
 
        Eg: Python objects like List, Tuple, Dictionary.

* Once Python program completes its execution then these objects will be destroyed automatically and data will be lost.

2.Permanent Storage Areas:
--------------------------------
* Also known as Persistent Storage Areas. Here we can store Data permanently.

      Eg: File Systems, Databases, Data warehouses, Big Data Technologies etc
      
File Systems:
---------------------
* File Systems can be provided by Local operating System. File Systems are best suitable to store very less Amount of Information.

Limitations:

    1) We cannot store huge Amount of Information.
    2) There is no Query Language support and hence operations will become very complex.
    3) There is no Security for Data.
    4) There is no Mechanism to prevent duplicate Data. Hence there may be a chance of Data Inconsistency Problems.

To overcome the above Problems of File Systems, we should go for Databases.

Databases:
--------------
    1) We can store Huge Amount of Information in the Databases.
    2) Query Language Support is available for every Database and hence we can perform Database Operations very easily.
    3) To access Data present in the Database, compulsory username and pwd must be required. Hence Data is secured.
    4) Inside Database Data will be stored in the form of Tables. While developing Database Table Schemas, Database Admin follow various Normalization 
        Techniques and can implement various Constraints like Unique Key Constrains, Primary Key Constraints etc which prevent Data Duplication. 
        Hence there is no chance of Data Inconsistency Problems.
        
        
Python Database Programming:
-----------------------------
* Sometimes as the part of Programming requirement we have to connect to the database and we
  have to perform several operations like creating tables, inserting data,updating data,deleting
  data,selecting data etc.
* We can use SQL Language to talk to the database and we can use Python to send those SQL commands to the database.
* Python provides inbuilt support for several databases like Oracle, MySql, SqlServer, GadFly, sqlite, etc.
* Python has seperate module for each database.

        Eg: cx_Oralce module for communicating with Oracle database
            pymssql module for communicating with Microsoft Sql Server
            
 Python Application Communicating With MySQL Database
 --
 * First We need to install MySQL in our machine
 * Python needs a MySQL driver to access the MySQL database.
 * Install mysql driver using pip tool
 * PIP is most likely already installed in your Python environment.
 
          pip install mysql-connector-python
          
Test MySQL Connector
------
* To test if the installation was successful, or if you already have "MySQL Connector" installed, create a Python page with the following content

          import mysql.connector
          

Create Connection:
------
* Start by creating a connection to the database.
* Use the username and password from your MySQL database

demo.py
--

            import mysql.connector

            mydb = mysql.connector.connect(
              host="localhost",
              user="yourusername",
              password="yourpassword"
            )

            print(mydb)
 
Creating a Database
--
* To create a database in MySQL, use the "CREATE DATABASE" statement

demo.py
--

          import mysql.connector

          mydb = mysql.connector.connect(
            host="localhost",
            user="yourusername",
            password="yourpassword"
          )

          mycursor = mydb.cursor()

          mycursor.execute("CREATE DATABASE mydatabase")
 

Check if Database Exists
--
* You can check if a database exist by listing all databases in your system by using the "SHOW DATABASES" statement

demo.py
--

        import mysql.connector

        mydb = mysql.connector.connect(
          host="localhost",
          user="yourusername",
          password="yourpassword"
        )

        mycursor = mydb.cursor()

        mycursor.execute("SHOW DATABASES")

        for x in mycursor:
          print(x)

Connecting with Existing Database
--
demo.py
-
        import mysql.connector

        mydb = mysql.connector.connect(
          host="localhost",
          user="yourusername",
          password="yourpassword",
          database="mydatabase"
        )











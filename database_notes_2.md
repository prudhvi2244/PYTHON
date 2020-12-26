Trainer : Raj Prudhvi ( Oracle Certified )
-

Creating a Table
-
* To create a table in MySQL, use the "CREATE TABLE" statement.
* Make sure you define the name of the database when you create the connection

customers.py
-

      import mysql.connector

      mydb = mysql.connector.connect(
        host="localhost",
        user="yourusername",
        password="yourpassword",
        database="mydatabase"
      )

      mycursor = mydb.cursor()

      mycursor.execute("CREATE TABLE customers (name VARCHAR(255), address VARCHAR(255))")
      
      
Check if Table Exists
--
* You can check if a table exist by listing all tables in your database with the "SHOW TABLES" statement

customers.py
--

        import mysql.connector

        mydb = mysql.connector.connect(
          host="localhost",
          user="yourusername",
          password="yourpassword",
          database="mydatabase"
        )

        mycursor = mydb.cursor()

        mycursor.execute("SHOW TABLES")

        for x in mycursor:
          print(x)
          
          
Primary Key
--
* When creating a table, you should also create a column with a unique key for each record.
* This can be done by defining a PRIMARY KEY.
* We use the statement "INT AUTO_INCREMENT PRIMARY KEY" which will insert a unique number for each record. Starting at 1, and increased by one for each record.  

customers.py
--

        import mysql.connector

        mydb = mysql.connector.connect(
          host="localhost",
          user="yourusername",
          password="yourpassword",
          database="mydatabase"
        )

        mycursor = mydb.cursor()

        mycursor.execute("CREATE TABLE customers (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), address VARCHAR(255))")












          
          
          
          

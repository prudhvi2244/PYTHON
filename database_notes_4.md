Trainer : Raj Prudhvi ( Oracle Certified )
--

Python MySQL Select From
--

Select From a Table
--
* To select from a table in MySQL, use the "SELECT" statement

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

      mycursor.execute("SELECT * FROM customers")

      myresult = mycursor.fetchall()

      for x in myresult:
         print(x)
         
Selecting Columns
--
* To select only some of the columns in a table, use the "SELECT" statement followed by the column name(s)

customers.py

      import mysql.connector

      mydb = mysql.connector.connect(
        host="localhost",
        user="yourusername",
        password="yourpassword",
        database="mydatabase"
      )

      mycursor = mydb.cursor()

      mycursor.execute("SELECT name, address FROM customers")

      myresult = mycursor.fetchall()

      for x in myresult:
        print(x)
        
        
Using the fetchone() Method
--
* If you are only interested in one row, you can use the fetchone() method.
* The fetchone() method will return the first row of the result

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

        mycursor.execute("SELECT * FROM customers")

        myresult = mycursor.fetchone()

        print(myresult)




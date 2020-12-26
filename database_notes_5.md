Trainer : Raj Prudhvi ( Oracle Certified )
--

Python MySQL Where
--
Select With a Filter
--
When selecting records from a table, you can filter the selection by using the "WHERE" statement

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

      sql = "SELECT * FROM customers WHERE address ='Electronic City' "

      mycursor.execute(sql)

      myresult = mycursor.fetchall()

      for x in myresult:
        print(x)
        


Wildcard Characters
--
* You can also select the records that starts, includes, or ends with a given letter or phrase.
* Use the %  to represent wildcard characters

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

        sql = "SELECT * FROM customers WHERE address LIKE '%way%'"

        mycursor.execute(sql)

        myresult = mycursor.fetchall()

        for x in myresult:
          print(x)

Prevent SQL Injection
--
* When query values are provided by the user, you should escape the values.
* This is to prevent SQL injections, which is a common web hacking technique to destroy or misuse your database.
* The mysql.connector module has methods to escape query values

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

        sql = "SELECT * FROM customers WHERE address = %s"
        adr = ("HSR Layout", )

        mycursor.execute(sql, adr)

        myresult = mycursor.fetchall()

        for x in myresult:
          print(x)


















































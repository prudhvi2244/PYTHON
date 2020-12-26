Trainer : Raj Prudhvi ( Oracle Certified )
--

Python MySQL Drop Table
--
Delete a Table
--
* You can delete an existing table by using the "DROP TABLE" statement

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

        sql = "DROP TABLE customers"

        mycursor.execute(sql)
        
Drop Only if Exist
--
* If the the table you want to delete is already deleted, or for any other reason does not exist, you can use the IF EXISTS keyword to \
  avoid getting an error.
  
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

          sql = "DROP TABLE IF EXISTS customers"

          mycursor.execute(sql)

  
  
  
  
  
  
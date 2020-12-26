Python MySQL Insert Into Table
--

Insert Into Table
--
* To fill a table in MySQL, use the "INSERT INTO" statement.

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

        sql = "INSERT INTO customers (name, address) VALUES (%s, %s)"
        val = ("Raj Prudhvi", "Electronic City")
        mycursor.execute(sql, val)

        mydb.commit()

        print(mycursor.rowcount, "record inserted.")
        
        
        
Important!:
--
Notice the statement: mydb.commit(). It is required to make the changes, otherwise no changes are made to the table.


Insert Multiple Rows
--
* To insert multiple rows into a table, use the executemany() method.
* The second parameter of the executemany() method is a list of tuples, containing the data you want to insert

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

        sql = "INSERT INTO customers (name, address) VALUES (%s, %s)"
        val = [
          ('Raj', 'Electronic City'),
          ('Kiran', 'Silk Board'),
          ('Hannah', 'Mountain 21'),
          ('Michael', 'Valley 345'),
          ('Sandy', 'Ocean blvd 2'),
          ('Betty', 'Green Grass 1'),
          ('Richard', 'Sky st 331'),
          ('Susan', 'One way 98'),
          ('Vicky', 'Yellow Garden 2'),
          ('Ben', 'Park Lane 38'),
          ('William', 'Central st 954'),
          ('Chuck', 'Main Road 989'),
          ('Viola', 'Sideway 1633')
        ]

        mycursor.executemany(sql, val)

        mydb.commit()

        print(mycursor.rowcount, "was inserted.")








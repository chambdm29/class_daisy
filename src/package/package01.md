```
What is JDBC ?
Java Database Connectivity
--  Comes with JDK , work with relational database system
--  Its under java.sql package   import java.sql.* ;
--  It has set of Interfaces and classes to work with any RDBMS
How JDBC works
JDBC offers a programming-level interface that handles the mechanics of Java applications communicating
with a database or RDBMS. The JDBC interface consists of two layers:
1.The JDBC API supports communication between the Java application and the JDBC manager.
2.The JDBC driver supports communication between the JDBC manager and the database driver.
JDBC is the common API that your application code interacts with. Beneath that is the JDBC-compliant driver for the database you are using.
Java App   ------ JDBC ------- Actual Database
JDBC does not provide actual implementation.
Each RDBMS(database  like Oracle, MySQL, Postgress) will provide
actual implementation known as driver
We used the maven dependency to import this driver
<dependency>
<groupId>com.oracle.ojdbc</groupId>
<artifactId>ojdbc8</artifactId>
<version>21.1.0.0</version>
</dependency>
JDBC has DriverManager class to manage connection according to
the url, username , password
url | connection string  (YOU WILL BE GIVE THIS INFORMATION)
jdbc:oracle:thin:@54.88.118.39:1521:XE
"jdbc:oracle:thin:@IP_ADDRESS:1521:XE";
jdbc  --  connection using java
oracle -- database vendor , RDBMS
thin  --- one type oracle driver
IP_ADDRESS  -- HOSTNAME or IP
1521  ---- port used for oracle database
XE   ----- sid name  unique identifier for your oracle db
3 important Interfaces in JDBC
Connection
This interface represents the connection with a specific database.
SQL statements are executed in the context of a connection.
DriverManager will look at the url, username password that you provided and connect.
Connection connection = DriverManager.getConnection(url,username,password)
Statement
This interface represents a static SQL statement.
Using the Statement object and its methods, you can execute an SQL statement and get the results of it
You need to use Connection object created above to create Statement object
There are 2 ways to create statement object
Statement statement = connection.createStatement();
//default statement will be able to only move forward in resultset
// this will be used to created ResultSet that can move freely
Statement statement= conn.createStatement(ResultSet.TYPE_SCROLL_INSENSITIVE,ResultSet.CONCUR_READ_ONLY );
ResultSet
Resultset will store the query result (the query that you want to run)
ResultSet resultSet = statement.executeQuery("SELECT * FROM employees");
Connection , Statement , ResultSet are all resources need to be closed after usage
call the close method to close at the end of the code
connection.close();
statement.close();
resultSet.close();
Getting the data from database
getString(ColumName)
getString(Index)
getInt(ColumName)
getInt(Index)
getDouble(ColumName)
getDouble(Index)
getDate(ColumName)
getDate(Index)
rs.getString(1) --->> return the first column cell value at this row
rs.getString("column name") --->> return the cell value at this column at this row
----- other methods available under ResultSet class
rs.next()       // is used to move the cursor to the one row next from the current position.
rs.previous()   // is used to move the cursor to the one row previous from the current position.
rs.first()        // is used to move the cursor to the first row in result set object.
rs.last()     // is used to move the cursor to the last row in result set object.
rs.beforeFirst()  // back to before first row location
rs.afterLast()       // move to the after last row location
rs.absolute(rowNum)   // is used to move the cursor to the specified row number in the ResultSet object.
resultSet.getRow()
// ResultSetMetadata is data about the ResultSet like column count , column name
// any many more info about the ResultSet itself
// getMetaData method will return ResultSetMetaData object
ResultSetMetaData rsmd = rs.getMetaData();
// counting how many columns we have in our ResultSet object
int columnCount =  rsmd.getColumnCount() ;
System.out.println("columnCount = " + columnCount);
// find out column name according to the index
String secondColumnName = rsmd.getColumnName(2);
System.out.println("secondColumnName = " + secondColumnName);
Collapse
```



Try me!
white_check_mark
eyes
raised_hands













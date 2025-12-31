# java
## JDBC
###
JDBC stands for Java DataBase Connectivity

JDBC is a specification for developing database applications by using java 

- Specification is a set of rules and guidelines that are used to develop environment and application
- An application that communicates with the database is known as database application
- An application is a program in which we interact in with on the desktop
- Database is a software and it is an organized collection of data, data organized in form of tables
- Application is frontend (client) and database is backend (server)
-  client is a software that sends the request to the server to get response
-  server is a software that recieves request from the client, process the request, constructs the response and sends the response back to client
-  application communicates with database by using SQL
-  SQL stands for Structured Query Language and it is used by application to communicate with database
-  database software contains database application(SQL prompt) and database(oracle)
### DRIVER
A driver is a software and it is used to connect application and database,
There are 2 categories in driver
1) ODBC (Open Database Connectivity) driver
2) JDBC (Java Database connectivity) driver

- Non java application are connected with database using ODBC drivers, all ODBC drivers are part of ODBC tool
- java application connection are failed because of compatability to solve the problem JDBC drivers are introduced.

There are 4 types of JDBC drivers
1) TYPE-1 DRIVER (JDBC ODBC BRIDGE DRIVER)
2) TYPE-2 DRIVER (JDBC NATIVE API DRIVER)
3) TYPE-3 DRIVER (JDBC NETWORK PROTOCOL DRIVER)
4) TYPE-4 DRIVER (JDBC 100% PURE JAVA DRIVER)


Two ways to connect java application with database 
1) by using JDBC and ODBC drivers (TYPE-1)
2) by using JDBC driver only (TYPE-2 | TYPE-4)

### STEPS TO DEVELOP DATABASE APPLICATION

1) Load a speccific JDBC driver
2) Establish connection between database and java application
3) perform the task
4) close the connection
### TYPE-4 DRIVER is the most commonly used JDBC driver.

STEP 1
- To load JDBC driver we use **forName** method
- the method present in Class classname and return type is class

TYPE-4 DRIVER

  Class c=Class.forName("oracle.jdbc.driver.OracleDriver")

STEP 2
- To establish connection between database and application we use *getConnection* method
- the method present in DriverManager class and return type is Connection

CONNECTION

  Connection con=DriverManager.getConnection(URL,"USERNAME","PASSWORD");
  URL OF TYPE-4 DRIVER- "jdbc:oracle:thin:@localhost:1521:XE"
STEP 3
  we can execute static,dynamic queries and PL/SQL programs

### JDBC api
- It is a java api that can access any kind of tabular data.
- In JDBC API, the packages used are:
  1) java.sql package
  2) javax.sql package
  3) javax.sql.rowset package

### java.sql package 
- The java.sql package contains classes and interfaces required to interact with databases using JDBC.
  1) classes
     - DriverManager
     - SQLException
     - Date
     - Time
     - Types
  2) interfaces
     - Driver
     - Connection
     - Statement
     - PreparedStatement
     - CallableStatement
     - ResultSet
     - ResultSetMetaData
     - DatabaseMetaDate
     - Blob
     - Clob

### java.sql.connection
the method we use from connection interfaces are
1) public abstract Statement createStatement() Used for static SQL queries
2) public abstract PreparedStatement prepareStatement(String) Used for dynamic (parameterized) SQL queries
3) public abstract CallableStatement prepareCall(String) Used to execute stored procedures (PL/SQL programs)

### java.sql.Statement 
The Statement interface is used to execute static SQL queries.

METHODS
1) public abstract boolean execute(String) suitable for DDL queries
2) public abstract int executeUpdate(String) suitable for DML queries
3) public abstract ResultSet executeQuery(String) suitable for DQL queries


### RESULTSET

- ResultSet is an object that encapsulates set of rows from database

- ResultSet is generated based on the Sql query (SELECT)

### java.sql.ResultSet
METHODS
- public abstract boolean next() throws SQLException -> returns true and moves the cursor to next record if present
- public abstract String getString(int) throws SQLException
- public abstract int getInt(int) throws SQLException

the above two methods are for getting the data from the ResultSet
- public abstract ResultSetMetaData getMetaData() throws SQLException -> returns the ResultSetMetaData

METADATA - data about data

ResultSetMetaData - data about ResultSet (column names)

### java.sql.ResultSetMetaData
Methods
- public abstract int getCoulmnCount() throws SQLException -> return number of columns
- public abstract String getColumnName(int) throws SQLException -> return column name based on the specified column index

### java.sql.PreparedStatement 
The PreparedStatement interface is used to execute dynamic SQL queries.

METHODS
- public abstract void setInt(int,int) throws SQLException -> the first argument refers to the index and second refers to the integer value that to be set or filled in the data
- public abstract void setString(int,String) throws SQLException -> same as above instead of integer value it takes string value to fill in the data
- public abstract int excuteUpdate() throws SQLException -> to execute the DML query
- public abstract ResultSet excutequery() throws SQLException -> to execute DQL query

## PROGRAMS 

1) PROGRAM FOR ESTABLISHING CONNECTION BETWEEN JAVA APPLICATION AND DATABASE BY USING JDBC TYPE-4 DRIVER --> *DemoConnection.java*
2) PROGRAMS FOR ALL STATIC QUERIES
   - JDBC PROGRAM FOR ALL DDL COOMANDS  --> **CreateTable.java**
     - In this program we used CREATE command, the process is same and we can use all the DDL commands in the program
   - JDBC PROGRAM FOR ALL DML COOMANDS  --> **InsertCommand.java**
     - In this program we used INSERT command, the process is same and we can use all the DML commands in the program
   - JDBC PROGRAM FOR DQL COOMANDS  --> **SelectCommand.java**
     - In this program we used SELECT command
3) PROGRAMS FOR ALL DYNAMIC QUERies
   - JDBC PROGRAM FOR ALL DML COOMANDS  --> **DynamicInsert.java**
     - In this program we used INSERT command, the process is same and we can use all the DML commands in the program
   - JDBC PROGRAM FOR DQL COOMAND --> **DynamicSelect.java**
4) PROGRAMS FOR PL/SQL PROGRAM
   - JDBC PROGRAM TO DEMONSTRATE CALLABLESTATEMENT WITH INPUT PARAMATERS IN A STORED PROCEDURE --> **PlSqlProcedure.java**
     - In the program we stored a procedure in database and used it in the java program, what we have done in the program is we are inserting the data dynamically using preparedstatement interface
   - JDBC PROGRAM TO DEMONSTRATE CALLABLESTATEMENT WITH OUTPUT PARAMATERS IN A STORED PROCEDURE --> **PlSqlGetProcedure.java**
     - In the program we stored a procedure in database and used it in the java program, what we have done in the program is we inserted data dynamically and got an output as per the input
   - JDBC PROGRAM TO DEMONSTRATE CALLABLESTATEMENT WITH FUNCTION -->  **PlSqlFunction.java**
     - In the program we stored a function in database and used it in the java program



    




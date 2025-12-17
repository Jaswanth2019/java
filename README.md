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

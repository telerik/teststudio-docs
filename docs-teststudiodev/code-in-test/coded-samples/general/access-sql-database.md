---
title: Access SQL Database
page_title: Access SQL Database - Test Studio Dev Documentation
description: Access SQL Database
position: 1
---
# How to Access a SQL Database in Code

You can access an SQL database in a data driven test, as seen <a href="/features/data-driven-testing/add-data-source#add-a-database-source" target="_blank">here</a>. This is a built-in functionality for Test Studio Dev but if
you need to establish the connection in code the connection and interaction with the database need to be established step by step. This article demonstrates how to access an Oracle database through code.

## Add Assembly Reference

To use the *System.Data.OracleClient* API which is part of the *System.Data* assembly add reference to it. Its default location (on a 64-bit Windows 7 machine with .NET 4.0) is: 

    C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.0\Profile\Client\System.Data.dll

If a reference to System.Data 2.0 already exists, remove it and add it from the above location to point to its 4.0 version.

Ensure you add the *using* or *Imports* statement to the top of the code-behind file.

````C#
    using System.Data.SqlClient;
````
````VB
    Imports System.Data.SqlClient;
````

## Sample Code

Here is a SQL database named **myFirstDB** with a table named **Table_1** and column named **City** in it.

![Database][1]

### Read from SQL Database

````C#
    //Define a new SQL connection with a connection string. 
    //The connection string will be different depending on your environment and the name of the database, table, etc.
    //See http://www.connectionstrings.com for connection string examples.
    SqlConnection thisConnection = new SqlConnection("Data Source=MACHINENAME\\SQLEXPRESS; Initial Catalog=myFirstDB; Integrated Security=true;"); 
    thisConnection.Open();
 
    //Write the name of the database to the log
    Log.WriteLine(thisConnection.Database);
 
    //Create an SQL command
    SqlCommand thisCommand = thisConnection.CreateCommand();
 
    //This is a simple SQL command that will go through all the values in the "City" column from the table "Table_1"
    thisCommand.CommandText = "SELECT City FROM Table_1";
    SqlDataReader thisReader = thisCommand.ExecuteReader();
    while (thisReader.Read())
    {
        Log.WriteLine("Value of City column: " + (String) thisReader["City"]);
    }
 
    thisReader.Close();
    thisConnection.Close();
````
````VB
    'Define a new SQL connection with a connection string. 
    'The connection string will be different depending on your environment and the name of the database, table, etc.
    'See http://www.connectionstrings.com for connection string examples.
    Dim thisConnection As New SqlConnection("Data Source=MACHINENAME\SQLEXPRESS; Initial Catalog=myFirstDB; Integrated Security=true;")
    thisConnection.Open()
    
    'Write the name of the database to the log
    Log.WriteLine(thisConnection.Database)
    
    'Create an SQL command
    Dim thisCommand As SqlCommand = thisConnection.CreateCommand()
    
    'This is a simple SQL command that will go through all the values in the "City" column from the table "Table_1"
    thisCommand.CommandText = "SELECT City FROM Table_1"
    Dim thisReader As SqlDataReader = thisCommand.ExecuteReader()
    While thisReader.Read()
        Log.WriteLine("Value of City column: " + DirectCast(thisReader("City"), [String]))
    End While
    
    thisReader.Close()
    thisConnection.Close()
````

### Write into SQL Database

````C#
    //Define a new SQL connection with a connection string.
    //The connection string will be different depending on your environment and the name of the database, table, etc.
    //See http://www.connectionstrings.com for connection string examples.
    SqlConnection thisConnection = new SqlConnection("Data Source=MACHINENAME\\SQLEXPRESS; Initial Catalog=myFirstDB; Integrated Security=true;");
    thisConnection.Open();
 
    //Write the name of the database to the log.
    Log.WriteLine(thisConnection.Database);
 
    //Create a SQL command to insert a new value into the "City" column.
    SqlCommand thisCommand = thisConnection.CreateCommand();
    thisCommand.CommandText = "INSERT INTO Table_1 (City) VALUES ('Richmond')";
    thisCommand.ExecuteNonQuery();
````
````VB
    'Define a new SQL connection with a connection string.
    'The connection string will be different depending on your environment and the name of the database, table, etc.
    'See http://www.connectionstrings.com for connection string examples.
    Dim thisConnection As New SqlConnection("Data Source=MACHINENAME\SQLEXPRESS; Initial Catalog=myFirstDB; Integrated Security=true;")
    thisConnection.Open()
 
    'Write the name of the database to the log.
    Log.WriteLine(thisConnection.Database)
 
    'Create a SQL command to insert a new value into the "City" column.
    Dim thisCommand As SqlCommand = thisConnection.CreateCommand()
    thisCommand.CommandText = "INSERT INTO Table_1 (City) VALUES ('Richmond')"
    thisCommand.ExecuteNonQuery()
````

**Note**: The example requires to be modified as per the databse which will be used as data source. 

[1]: images/access-sql-database/fig1.png
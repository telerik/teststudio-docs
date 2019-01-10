---
title: Access Oracle Database
page_title: Access Oracle Database
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#How to Access an Oracle Database in Code#

Oracle database could be used as data source in a data driven test as described <a href="/features/data-driven-testing/add-data-source#add-a-database-source" target="_blank">here</a>. This is a built-in functionality for Test Studio but if using the Telerik Testing Framework the connection and interaction with the database need to be established step by step. This article demonstrates how to access an Oracle database through code.

##Install Oracle Client##

To access the Oracle database in C# it is necessary to install <a href="http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html" target="_blank">**Oracle Data Access Components**</a>. That driver package contains the necessary libraries to refer in the project.

##Add an Assembly Reference##

Once the ODAC is installed the following dll have to be <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">referred</a> in the project:

	Oracle.DataAccess.dll

For default installation the dll file could be found in the Oracle data base installation folder:

	C:\Oracle\DB\app\oracle\product\11.2.0\server\odp.net\bin\4

Include the following *usings* in the code.

```C#
using Oracle.DataAccess.Client;
using Oracle.DataAccess.Types;
```
```VB
import Oracle.DataAccess.Client
import Oracle.DataAccess.Types
```

##Data Connection String##

An Oracle connection string is required to identify the database to connect to. Here is an example:

```
Data Source=XE;User Id=SYSTEM;Password=pass;
```

Different connection strings could be used. See <a href="https://www.connectionstrings.com/oracle/" target="_blank">here</a> for more examples.

##Sample Code##

This code runs a simple query against a database table similar to <a href="/features/data-driven-testing/oracle-db-example" target="_blank">this example</a>:

```C#
string oradb = "Data Source=XE;User Id=SYSTEM;Password=pass;";

OracleConnection conn = new OracleConnection(oradb);

conn.Open();

OracleCommand cmd = new OracleCommand 
{
    Connection = conn,
    CommandType = System.Data.CommandType.Text
};

// SQL querry:
cmd.CommandText = "select Name from Employees where ID=2" ;

OracleDataReader dr = cmd.ExecuteReader();

dr.Read();

// Print the datavalue in the execution log
Log.WriteLine(dr.GetString(0).ToString());

conn.Dispose();
```


>This code won't run without modification. The database, table, and column in the original code won't exist in your environment unless you create the same database.

For additional help on using Oracle database please visit <a href="http://www.oracle.com/webfolder/technetwork/tutorials/obe/db/dotnet/GettingStartedNETVersion/GettingStartedNETVersion.htm" target="_blank">the Oracle official help page</a>.

<br/>

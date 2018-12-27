---
title: Oracle Database Example
page_title: Oracle Database Example | Test Studio Dev Documentation
description: How to use Oracle DB for data driven testing with Test Studio Dev 
position: 1
---
# Oracle Database Example

This example is completed using an **Oracle Database Express** (Oracle Database XE) installed and configured instance.

> To be able to connect and work with the database from Test Studio it is necessary to install <a href="http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html" target="_blank">**Oracle Data Access Components**</a>.

Next step is to create a database in order to use it for data binding. One way to do it is by using <a href="http://www.oracle.com/technetwork/developer-tools/sql-developer/overview/index.html" target="_blank">Oracle SQL Developer</a>. On the following image there are SQL queries that will create table **Employees** and insert there two rows of data.

![Create Table][1]

Once the table is created it is possible to connect to it and use it for data-driven testing:

1.&nbsp; Click on **Add** from **Data Sources** menu: 

![Create Table][4]

2.&nbsp; In the **Create new data source** dialog - for **Data Source Types** choose **Database**

![Create New Data Source][2]

3.&nbsp; For **Provider**, select **Oracle Data Provider for .NET**

4.&nbsp; Here's an example for **Connection String**:

```
Data Source=XE;User Id=SYSTEM;Password=pass;
```

It is possible to create many different connection strings. See <a href="https://www.connectionstrings.com/oracle/" target="_blank">here</a> for more examples.

5.&nbsp; Customize the **Friendly Name** as desired.

6.&nbsp; Click **Create** and the new data source should appear in the Data Sources list.

<br/>

When a <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">test is bound</a> to this data base the table to be used will be specified:

![Bind To Table][3]

[1]: images/oracle-db-example/fig1.png
[2]: images/oracle-db-example/fig2.png
[3]: images/oracle-db-example/fig3.png
[4]: images/oracle-db-example/fig4.png
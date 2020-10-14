---
title: Add a Data Source
page_title: Add an External Data Source to your Test Project
description: "How to add Excel/ CSV/ SQL Oracle DataBase/ external data source into a Test Studio project. How to add the data source for data driven test in Test Studio"
previous_url: /user-guide/data-driven-testing/add-a-data-source.aspx, /user-guide/data-driven-testing/add-a-data-source
position: 2
---
# Add an External Data Source To Your Test Project

> When adding an external data file to your project, a copy of that file is placed in your project's Data folder. This is from where the file is accessed and any changes should be made to the file in this location.

The default path in Windows 7 is:

- **C:\Users\User\Documents\Test Studio Projects\Project Name\Data**

Jump to the following sections:

- [Excel spreadsheet](#add-an-excel-spreadsheet)
- [XML file](#add-an-xml-file)
- [CSV file](#add-a-csv-file)
- [Database source](#add-a-database-source)

## Add an Excel Spreadsheet

It is important to note that the entries in the first row of the Excel spreadsheet are used as the column names when attaching columns to the inputs.

![Excel][1]

In the above example, *Input A* is the name of the first column, *Input B* is the name of the second column, and *Results* is the name of the third column. You use these names when attaching the columns to the input values of the test steps.

> For numeric-only fields, you may need to add an apostrophe, also known as a single quote character ( ' ), to the beginning of the number for the data to render correctly in Test Studio. This is an Excel command to store the number as text.

<table id="no-table">
<tr>
<td>![Excel Standalone][2]<br> **Standalone Version** <br>From the **Project tab**, click **Add > Excel File**.</td>
<td>![Excel VS][3]<br>**VS Plugin**<br>Open the data source drop-down by clicking its down arrow, then **Add New > Excel**.
</td>
</tr>
<table>

The **Create new data source** dialog opens:

![Create new datasource][4]

Enter the path to your Excel file or click the "..." button to browse and select it. Click OK to save this data source definition.

<table id="no-table">
<tr>
<td>![Standalone][5]<br>**Standalone Version**<br>The **Bind Test** button is now enabled in the Project View ribbon bar.</td>
<td>![VS Plugin][6]<br>**VS Plugin**<br>Click **Yes** to open the **Bind test to data source** dialog, which is discussed in the next section.</td>
<td>![Solution expl][7]<br>A new entry is added to the Data folder of your test project.</td>
</tr>
<table>

## Add an XML File

Here is an example of a basic XML file with two columns:

```xml
<Searches>
   <Search UserName="john.smith" Password="t3ler1k" />
   <Search UserName="bob.brown" Password="5ilverl1ght" />
   <Search UserName="sam.jones" Password="t3st5tudi0" />
</Searches>
```

*Search* is the equivalent of an Excel Sheet. *UserName* and *Password* translate as the column names. Use **$(UserName)** and **$(Password)** to data bind the applicable properties.

![Bind XML file][8]

## Add a CSV File

CSV files can be created in any spreadsheet application or directly in Notepad if you follow the *.csv formatting conventions (each line with comma separated values, the same number of commas in each line).


Here is an example of a basic CSV file with two columns:

![CSV file][9]

Just like an Excel spreadsheet, the first row of data will be used as the column names. Use **$(UserName)** and **$(Password)** to data bind the applicable properties.

## Add a Database Source

Adding a database source is different than adding an Excel spreadsheet, CSV, or XML file. When you select Database in the Create new data source dialog, you have a number of new options you need to specify in order to define your database connection.

- **Provider** - in this drop-down, select which database provider to use to access your database. The list that is displayed here depends on which providers have been installed on your computer. You should contact your database administrator if you are not sure what to select.
- **Connection String** - enter a valid connection string that is supplied to the selected Provider. The connection string instructs the provider the details on how to connect to your database.
- **Test** - click this button to test the connection to your database. A dialog indicating success will display if <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> makes a connection.
- **Friendly Name** - enter a name to represent this database connection definition. The name entered here is displayed in the Data Sources pane in the Standalone version and in the Data folder in the VS plugin.

![Database source][10]

**See also:**

- [How to connect to a SQL Database](/features/data-driven-testing/sql-database-example)

- [How to connect to an Oracle Database](/features/data-driven-testing/oracle-db-example)

[1]: /img/features/data-driven-testing/add-data-source/fig1.png
[2]: /img/features/data-driven-testing/add-data-source/fig2.png
[3]: /img/features/data-driven-testing/add-data-source/fig3.png
[4]: /img/features/data-driven-testing/add-data-source/fig4.png
[5]: /img/features/data-driven-testing/add-data-source/fig5.png
[6]: /img/features/data-driven-testing/add-data-source/fig6.png
[7]: /img/features/data-driven-testing/add-data-source/fig7.png
[8]: /img/features/data-driven-testing/add-data-source/fig8.png
[9]: /img/features/data-driven-testing/add-data-source/fig9.png
[10]: /img/features/data-driven-testing/add-data-source/fig10.png
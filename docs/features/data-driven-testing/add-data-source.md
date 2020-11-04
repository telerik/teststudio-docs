---
title: Add External Data Source
page_title: Add External Data Source to Your Test Project
description: "How to add Excel/ CSV/ SQL Oracle DataBase/ external data source into a Test Studio project. How to add the data source for data driven test in Test Studio"
position: 2
---
# Add External Data Source To Your Test Project

Test Studio supports multiple external data types to be used as a source for data driven testing. In this article you can find a list of the supported data files and how to reference these in a Test Studio project.

- [Excel spreadsheet](#add-an-excel-spreadsheet)
- [XML file](#add-an-xml-file)
- [CSV file](#add-a-csv-file)
- [Database source](#add-a-database-source)

If you have already added an external data source to your project, follow <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">this link and check how to bind this data source to a test</a>.

## Add an Excel Spreadsheet

In the below section you can read how to prepare the Excel file and add it to the Test Studio project.

### Prepare the Excel File

> __Note__
><br>
><br>
> When preparing the Excel data sheet, consider that the __first row of the Excel spreadsheet is used to define the column names__ when binding data to the steps.

![Excel][1]

In the above example, *Input A* is the name of the first column, *Input B* is the name of the second column, and *Results* is the name of the third column. You __use these names when attaching the columns to the input values__ of the test steps.

> __Tip__
><br>
><br>
> For __numeric-only fields, you may need to add an apostrophe__, also known as a single quote character ( ' ), to the beginning of the number for the data to render correctly in Test Studio. This is an Excel command to store the number as text.

### Add the Excel File to Project

Click the __Add__ button in the _Data Sources_ section of the _Project_ tab to open the **Create new data source** dialog.

![add-data-source](/img/automated-tests/data-drive-test/bind-test-data-source/add-data-source.png)

Ensure the selected type of file is the Excel. Then enter the path to the prepared Excel file, or click the _three dots_ button ("...") to browse and select it from your local disk. Click the __Create__ button to save this data source definition in the project.

![Create new data source][4]

## Add an XML File

In the below section you can read how to prepare the XML file and add it to the Test Studio project.

### Prepare the XML File

XML files are type of documents that both humans and machines can read. The structure of the document is defined by tags and Test Studio uses these to define the data source values. Here is an example of a basic XML file with two columns:

```xml
<Searches>
   <Search UserName="john.smith" Password="johnspass" />
   <Search UserName="bob.brown" Password="bobspass" />
   <Search UserName="sam.jones" Password="samspass" />
</Searches>
```

*Search* is the equivalent of an Excel Sheet. *UserName* and *Password* translate as the column names.

### Add the XML File to Project

Click the __Add__ button in the _Data Sources_ section of the _Project_ tab to open the **Create new data source** dialog.

![Bind XML file][8]

Ensure the selected type of file is the XML. Then enter the path to the prepared XML file, or click the _three dots_ button ("...") to browse and select it from your local disk. Click the __Create__ button to save this data source definition in the project.

## Add a CSV File

In the below section you can read how to prepare the CSV file and add it to the Test Studio project.

### Prepare the CSV File

CSV files can be created in any spreadsheet application or directly in Notepad if you follow the *.csv formatting conventions - each line with comma separated values, the same number of commas in each line. Here is an example of a basic CSV file with two columns:

![CSV file][9]

Just like an Excel spreadsheet, the first row of data will be used to define the column names - *UserName* and *Password*.

### Add the CSV File to Project

Click the __Add__ button in the _Data Sources_ section of the _Project_ tab to open the **Create new data source** dialog.

![Bind CSV file][9a]

Ensure the selected type of file is the CSV. Then enter the path to the prepared CSV file, or click the _three dots_ button ("...") to browse and select it from your local disk. Click the __Create__ button to save this data source definition in the project.

## Add a Database Source

Adding a database source requires additional details compared to adding an Excel spreadsheet, CSV, or XML file. When you select Database in the __Create new data source__ dialog, you have a number of new options, which you need to specify in order to define your database connection.

- **Provider** - select which database provider to use to access your database. The list, that is displayed in this drop-down, depends on which providers have been installed on your computer. If you are not sure what to select, you can contact your database administrator.
- **Connection String** - enter a valid connection string that is supplied to the selected Provider. The connection string instructs the provider the details on how to connect to your database.
- **Test** - click this button to test the connection to your database. A dialog indicating success will display if the connection is established.
- **Friendly Name** - enter a name to represent this database connection definition. The name entered here is displayed in the _Manage Data Sources_ window.

![Database source][10]

> __Tip__
><br>
><br>
> Find examples for **[How to connect to a SQL Database](/features/data-driven-testing/sql-database-example)** and **[How to connect to an Oracle Database](/features/data-driven-testing/oracle-db-example)**.

[1]: /img/features/data-driven-testing/add-data-source/fig1.png
[2]: /img/features/data-driven-testing/add-data-source/fig2.png
[3]: /img/features/data-driven-testing/add-data-source/fig3.png
[4]: /img/features/data-driven-testing/add-data-source/fig4.png
[5]: /img/features/data-driven-testing/add-data-source/fig5.png
[6]: /img/features/data-driven-testing/add-data-source/fig6.png
[7]: /img/features/data-driven-testing/add-data-source/fig7.png
[8]: /img/features/data-driven-testing/add-data-source/fig8.png
[9]: /img/features/data-driven-testing/add-data-source/fig9.png
[9a]: /img/features/data-driven-testing/add-data-source/fig9a.png
[10]: /img/features/data-driven-testing/add-data-source/fig10.png
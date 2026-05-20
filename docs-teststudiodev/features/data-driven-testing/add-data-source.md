---
title: Add a Data Source
page_title: Add an External Data Source to your Test Project - Test Studio Dev Documentation
description: How to add an external file to be used for data driven testing with Test Studio Dev 
position: 2
---
# Add an External Data Source To Your Test Project

> When adding an external data file to your project, a copy of that file is placed in the _Data_ folder under the project's root folder. This is from where the file is accessed and any changes should be made to the file in this location.

## Add an Excel Spreadsheet

The first row entries in the Excel spreadsheet are used as column names when attaching columns to the inputs. In this example, *Input A* is the name of the first column, *Input B* is the name of the second column, and *Results* is the name of the third column and these will be used to identify the columns to attach to the input values of the test steps.

![Excel](images/add-data-source/fig1.png)

> _Note!__ For numeric-only fields, you may need to add an apostrophe, also known as a single quote character ( ' ), to the beginning of the number for the data to render correctly in Test Studio. This is an Excel command to store the number as text.

Open the data source dropdown by clicking its button down arrow, then select **Add New > Excel**.

![Excel VS](images/add-data-source/fig3.png)

The **Create new data source** dialog opens:

![Create new datasource](images/add-data-source/fig4.png)

Enter the path to your Excel file or click the "..." button to browse and select it. Click _Create_ to save this data source definition. A new entry is added to the Data folder of your test project.

![Solution expl](images/add-data-source/fig7.png)

Click Ok to confirm binding the current test to the Excel data file.

![Confirm](images/add-data-source/fig6.png)

Then select data source and data table in the _Bind test to data source_ dialog to see the Excel sheet data bound to the test. 

<table id="no-table">
<tr>
<td>![Select Data source](images/add-data-source/fig11.png)</td>
<td>![Select Data table](images/add-data-source/fig12.png)</td>
<td>![Preview bound data](images/add-data-source/fig13.png)</td>
</tr>
<table>

## Add an XML File

Here is an example of a basic XML file with two columns:

````XML
<Searches>
   <Search UserName="john.smith" Password="t3ler1k" />
   <Search UserName="bob.brown" Password="5ilverl1ght" />
   <Search UserName="sam.jones" Password="t3st5tudi0" />
</Searches>
````

*Search* is the equivalent of an Excel Sheet. *UserName* and *Password* translate as the column names. Use **$(UserName)** and **$(Password)** to data bind the applicable properties.

![Bind XML file](images/add-data-source/fig8.png)

## Add a CSV File

CSV files can be created in any spreadsheet application or directly in Notepad if you follow the *.csv formatting conventions (each line with comma separated values, the same number of commas in each line).

Here is an example of a basic CSV file with two columns:

![CSV file](images/add-data-source/fig9.png)

Just like an Excel spreadsheet, the first row of data will be used as the column names. Use **$(UserName)** and **$(Password)** to data bind the applicable properties.

## Add a Database Source

Adding a database source is different than adding an Excel spreadsheet, CSV, or XML file. When you select Database in the Create new data source dialog, you have a number of new options you need to specify in order to define your database connection.

- **Provider** - in this drop-down, select which database provider to use to access your database. The list that is displayed here depends on which providers have been installed on your computer. You should contact your database administrator if you are not sure what to select.
- **Connection String** - enter a valid connection string that is supplied to the selected Provider. The connection string instructs the provider the details on how to connect to your database.
- **Test** - click this button to test the connection to your database. A dialog indicating success will display if <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> makes a connection.
- **Friendly Name** - enter a name to represent this database connection definition. The name entered here is displayed in the Data Sources pane in the Standalone version and in the Data folder in the VS plugin.

![Database source](images/add-data-source/fig10.png)

Once you have added the data source you could proceed to <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">__bind a test to that data source__</a>. 

__See Also:__

* <a href="/advanced-topics/data-driven-testing/sql-database-example" target="_blank">How to connect a SQL Database to be used for data source</a>
*  <a href="/advanced-topics/data-driven-testing/oracle-db-example" target="_blank">How to connect an Oracle Database to be used for data source</a>


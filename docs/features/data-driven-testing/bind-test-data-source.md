---
title: Bind Test to External Data Source
page_title: Bind Test to External Data Source
description: "How to add/use a data source for a test in Test Studio. Bind a test to external data source. Bind test to an excel sheet. Bind test to XML file. Bind test to a database. Bind test to an SCV file. "
position: 3
---
# Bind Test to External Data Source

Test Studio allows you to use external data files for data driven testing. In this article you can read how to associate a test to an external data source.

If you have already related the external data source to a test in the project, follow <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">this link to go through a complete scenario for data driven test with external data source</a>.

## Bind the External Data Source to Test

Once you have <a href="/features/data-driven-testing/add-data-source" target="_blank">added a data source definition to your test project</a>, you are ready to bind your test to that data source.

Choose a test from the _Project Explorer_ and click the __Bind Test__ button from the _Data Source_ section in the _Project_ ribbon.

![choose-test-to-bind](/img/automated-tests/data-drive-test/bind-test-data-source/choose-test-to-bind.png)

The **Bind test to data source** dialog opens. Click the **Select Data Source** drop-down and choose the data source you just defined in the previous section. If your source is an Excel spreadsheet, choose which sheet from the spreadsheet to use. Once you select a sheet, the data from that sheet will be read and displayed in the dialog. Check out that the __first row of the spreadsheet is used to define the column names__.

<table id="no-table">
<tr>
<td>!![Bind test to data source window][3]</td>
<td>![Select Data Source][4]</td>
</tr>
<tr>
<td>Choose Data Source to Bind</td>
<td>Excel Sheet Selected</td>
</tr>
<table>

> __Note__
><br>
><br>
> You need to have __Microsoft Excel__ installed on this machine and/or the __Microsoft Access Database Engine 2010__ - see <a href="/troubleshooting-guide/test-execution-problems-tg/unable-to-show-data" target="_blank">this article</a> for more information.

## External Data Source Options

Some of the supported type of files to add as external data source allow you to limit the rows of it to use. This is applicable for Excel file or SQL database.

### Limit the Rows to Use from Excel File

If you need to use only part of the rows in an Excel sheet, you can enable the **Filter data between rows** box under the **Configure** section.

- If left unchecked, all data rows will be used during the test run.
- To limit which rows to use, check that box and select which rows you want to use by clicking the numeric up/down counters, and then **Update** to apply changes.

<table id="no-table">
<tr>
<td>![filter data][5]</td>
<td>![filter data][6]</td>
</tr>
<table>

### Use Specific Data from SQL Data Source

If your source is a SQL database, you can use a T-SQL query to select the data you want. Using T-SQL, you can get as complex as you need in your SQL select statement. Check out the example below.

![SQL database][7]

Once your select statement is entered, click the **Update** button to test the results - the **Preview** table shows these.

## Confirm Data Binding

When the external data source is set as desired, click the __OK__ button to bind it to the selected test. Now the external file is associated with the test and you can access the data values to bind the steps.

> __Tip__
><br>
><br>
> Refer to <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">the end-to-end scenario</a> how to continue with binding the steps to the added data.

## Remove Data Binding

To remove the external data source associated with a test, right click that test on the **Project** tab and select **Remove Data Binding**.

![Remove Data Binding][8]

[1]: /img/features/data-driven-testing/bind-test-data-source/fig1.png
[2]: /img/features/data-driven-testing/bind-test-data-source/fig2.png
[3]: /img/features/data-driven-testing/bind-test-data-source/fig3.png
[4]: /img/features/data-driven-testing/bind-test-data-source/fig4.png
[5]: /img/features/data-driven-testing/bind-test-data-source/fig5.png
[6]: /img/features/data-driven-testing/bind-test-data-source/fig6.png
[7]: /img/features/data-driven-testing/bind-test-data-source/fig7.png
[8]: /img/features/data-driven-testing/bind-test-data-source/fig8.png

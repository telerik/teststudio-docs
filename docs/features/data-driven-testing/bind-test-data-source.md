---
title: Bind Test to a Data Source
page_title: Bind Test to a Data Source
description: "How to add/use a data source for a certain test in Test Studio. Bind a test to the project data source."
previous_url: /user-guide/data-driven-testing/bind-test-to-data-source.aspx, /user-guide/data-driven-testing/bind-test-to-data-source
position: 3
---
# Bind Test to a Data Source

Now that you have added a data source definition to your test project, you are ready to bind your test to that data source.

<table id="no-table">
<tr>
<td>![Standalone][1]<br>**Standalone Version**</td>
<td>![VS Plugin][2]<br>**VS Plugin**</td>
</tr>
<table>

The **Bind test to data source** dialog opens:

![Bind test to data source][3]

Click the **Select DataSource** drop-down and choose the data source you just defined in the previous section. If your source is an Excel spreadsheet, choose which sheet from the spreadsheet to use. Once you select a sheet, the data from that sheet will be read and displayed in the dialog.

> You need to have __Microsoft Excel__ installed on this machine and/or the __Microsoft Access Database Engine 2010__ - see <a href="/troubleshooting-guide/test-execution-problems-tg/unable-to-show-data" target="_blank">this article</a> for more information.

![Select Data Source][4]

Note how the first row of the spreadsheet is used as the column names.

To limit which rows from the data source to use, check the **Filter data between rows** box under the **Configure** section.

- If left unchecked, all data rows will be used during the test run.
- To limit which rows to use, check that box and select which rows you want to use by clicking the numeric up/down counters, and then **Update** to apply changes.

<table id="no-table">
<tr>
<td>![filter data][5]</td>
<td>![filter data][6]</td>
</tr>
<table>

If your source is a SQL database, you have the option of using T-SQL to select the data you want. Using T-SQL, you can get as complex as you need in your SQL select statement. For example:

![SQL database][7]

After entering your select statement, click **Update** to test and display the selected data in the **Preview** table.

Click OK to bind this data source to your test.

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

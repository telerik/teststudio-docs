---
title: Manage Built-in Data Source
page_title: Manage Built-in Data Source
description: "Test Studio can use built-in data source for each test. Modify the built-in data source. Local data table in Test Studio test."
position: 1
---
# Manage Built-In Data Source

Test Studio provides internal data table, which can be used to data drive a test. A built-in data table is available in each web test and can only be used from this particular test.

This article describes what options there are in Test Studio to __maintain the content of the built-in table__ in order to drive test steps as desired. Follow <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">this link for a complete end-to-end scenario how to data drive a test using the built-in table</a>.

## Open the Local Data in Web Test

At the bottom of the test steps pane in the project you will see an additional tab named __'Local Data'__. Click this one to switch to the built-in data table.

![Standalone][2]

## Create a New Data Table

At the top of this pane there are few buttons and currently only **Create a new data table** is enabled. To add a new data grid, click this one. The default created grid has five columns and a single row.

![Create a new data table][4]

Along with this, the rest of the buttons get active and allows you to modify the grid.

## Modify the Data Table

Test Studio provides few options to easily modify a data table.

- __Set number of rows and columns__ (columns are limited to 50) and update the grid

![Set number of rows and columns][20]

- __Create new data table__ or __remove current data table__ (both will prompt you the current data will be lost if you proceed)

![Create new or remove data table][21]

- __Add a row/Delete the last row__ or __Add a column/Delete the last column__

<table id="no-table">
<tr>
<td>![Add/Delete Row][22]<br>Add/Delete Row</td>
<td>![Add/Delete Column][23]<br>Add/Delete Column</td>
</tr>
<table>

[2]: /img/features/data-driven-testing/local-data-driven-test/fig2.png
[4]: /img/features/data-driven-testing/local-data-driven-test/fig4.png
[20]: /img/features/data-driven-testing/local-data-driven-test/fig20.png
[21]: /img/features/data-driven-testing/local-data-driven-test/fig21.png
[22]: /img/features/data-driven-testing/local-data-driven-test/fig22.png
[23]: /img/features/data-driven-testing/local-data-driven-test/fig23.png

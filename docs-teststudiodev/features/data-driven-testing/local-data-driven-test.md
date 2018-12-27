---
title: Local Data Driven Test
page_title: Local Data Driven Test | Test Studio Dev Documentation
description: How to use local data table to data drive a test with Test Studio Dev
position: 1
---
# Local Data Driven Test

Let's create a new, Local Data Driven test. We'll go through five iterations of the test, each with a different search text.

1.Create a new Web Test and click Record.

2.Navigate to www.google.com, enter *Telerik* in the Google search box, and hit the Search button.

3.Click the **Pause recording** button in the <a href="/features/recorder/recorder-toolbar" target="_blank">Recording toolbar</a>.

![Pause recording][1]

4.Click the **Data** tab in the current test.

![Local Data][3]

5.There are few buttons at the top of this pane and at this point only **Create a new data table** is enabled. Click it to add a new data grid.

![Create a new data table][4]

6.The default grid will have five columns and a single row. Also the rest of the buttons get active and allows you to modify the grid.

- Set number of rows and columns (columns are limited to 50) and update the grid

![Set number of rows and columns][20]

- Create new data table or remove current data table (both will prompt you the current data will be lost if you proceed)

![Create new or remove data table][21]

- Add a row/Delete the last row or Add a column/Delete the last column

<table id="no-table">
<tr>
<td>![Add/Delete Row][22]<br>Add/Delete Row</td>
<td>![Add/Delete Column][23]<br>Add/Delete Column</td>
</tr>
<table>

7.For this example we want to execute five iterations of the test entering different search text for each iteration. Therefore modify the table to have a single column and 5 rows and click on _Update_. 

![Update the local data grid][5]

8.Enter random values in each of the cells in that column. Right click *Col1* and choose **Rename Column** to enter a meaningful to you name for the column. Then save the modified test.

![Enter values and rename the column][6]

9.Get back to the **Steps** tab and select step 2. This is the recorded step that sets the value of the Google search text box and open its properties in the Properties pane. 

![Enter Text Step][9]

10.Click the '...' button for the **(Bindings)** property and select the column name created in the local data to set it for the Text property of the selected step. Click the **Set** button.

![Bind step][12]

The data for the column in the local grid is now bound to the _Text_ property for the 'Enter text' step. Instead of entering _Telerik_ into the search box, the data stored in the data table will be entered. Save and execute the test. Note that the test will be executed for each row in the data table, for a total of five iterations.

[1]: images/local-data-driven-test/fig1.png
[3]: images/local-data-driven-test/fig3.png
[4]: images/local-data-driven-test/fig4.png
[5]: images/local-data-driven-test/fig5.png
[6]: images/local-data-driven-test/fig6.png
[9]: images/local-data-driven-test/fig9.png
[12]: images/local-data-driven-test/fig12.png
[20]: images/local-data-driven-test/fig20.png
[21]: images/local-data-driven-test/fig21.png
[22]: images/local-data-driven-test/fig22.png
[23]: images/local-data-driven-test/fig23.png

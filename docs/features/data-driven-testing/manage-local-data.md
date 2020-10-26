---
title: Manage Built-in Data Source
page_title: Manage Built-in Data Source
description: "Test Studio can use built-in data source for each test. Modify the built-in data source. Local data table in Test Studio test."
position: 1
---
# Manage Built-In Data Source

Test Studio provides internal data table, which can be used to data drive a test. A built-in data table is available in each web test and can only be used from this particular test.

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

__==================oldstuff-----------__
<table id="no-table">
<tr>
<td>![Standalone][2]<br>**Standalone Version**</td>
<td>![VS Plugin][3]<br>**VS Plugin**</td>
</tr>
<table>

5.There are few buttons at the top of this pane and currently only **Create a new data table** is enabled. Click it to add a new data grid.

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

9.Save the test.

10.Click the **Test Steps** at the button of the test or the **Step** tab in Visual Studio to return to the Test Steps View

<table id="no-table">
<tr>
<td>![Standalone][8]<br>**Standalone Version**</td>
<td>![VS Plugin][9]<br>**VS Plugin**</td>
</tr>
<table>

11.Data from an array can be used in recorded steps and code behind methods. To bind data from a data array to a recorded step, continue to the next step. To use reference data from the data array in a code behind method, skip to step 19.

12.Highlight step 2. This is the recorded step that sets the value of the Google search text box.

![Highlight step][10]

13.The properties for this step appear in the Properties pane, located on the right of the screen.

![Step properties][11]

14.Click the '...' button for **(Bindings)**.

15.Choose the **'Numbers'** from the drop down for **Text**.

![fig12][12]

16.Click the **Set** button.

![fig13][13]

17.The data for the column named Numbers from the data array is now bound to the Text property for that step. Instead of entering Telerik into the search box, the data stored in the array will be entered.

18.Save and execute the test. Note that the test will execute for each row in the data array, for a total of five iterations.

19.To use reference data from the data array in a code behind method, follow the below directions:

20.Highlight step 2. This is the recorded step that sets the value of the Google search text box. Right click the step and select Customize Step in Code.

21.Choose Visual Basic or C#.

22.Use the Data property followed by the index of the column to reference data from the grid. For example:

#### __[C#]__

	{{region }}

	//Reference a column by name
	Pages.Bing.SbFormQText.Text = Data["Numbers"].ToString();
	//Reference a column by index (zero based)
	Pages.Bing.SbFormQText.Text = Data[0].ToString();

	{{endregion}}

#### __[VB]__

	{{region }}

	'Reference a column by name
	Pages.Bing.SbFormQText.Text = Data("Numbers").ToString()
	'Reference a column by index (zero based)
	Pages.Bing.SbFormQText.Text = Data(0).ToString()

	{{endregion}}

23.Save and build project.

24.Execute your test. Note that the test will be executed for each row in the data array.

[1]: /img/features/data-driven-testing/local-data-driven-test/fig1.png
[2]: /img/features/data-driven-testing/local-data-driven-test/fig2.png
[3]: /img/features/data-driven-testing/local-data-driven-test/fig3.png
[4]: /img/features/data-driven-testing/local-data-driven-test/fig4.png
[5]: /img/features/data-driven-testing/local-data-driven-test/fig5.png
[6]: /img/features/data-driven-testing/local-data-driven-test/fig6.png
[7]: /img/features/data-driven-testing/local-data-driven-test/fig7.png
[8]: /img/features/data-driven-testing/local-data-driven-test/fig8.png
[9]: /img/features/data-driven-testing/local-data-driven-test/fig9.png
[10]: /img/features/data-driven-testing/local-data-driven-test/fig10.png
[11]: /img/features/data-driven-testing/local-data-driven-test/fig11.png
[12]: /img/features/data-driven-testing/local-data-driven-test/fig12.png
[13]: /img/features/data-driven-testing/local-data-driven-test/fig13.png
[14]: /img/features/data-driven-testing/local-data-driven-test/fig14.png
[15]: /img/features/data-driven-testing/local-data-driven-test/fig15.png
[20]: /img/features/data-driven-testing/local-data-driven-test/fig20.png
[21]: /img/features/data-driven-testing/local-data-driven-test/fig21.png
[22]: /img/features/data-driven-testing/local-data-driven-test/fig22.png
[23]: /img/features/data-driven-testing/local-data-driven-test/fig23.png

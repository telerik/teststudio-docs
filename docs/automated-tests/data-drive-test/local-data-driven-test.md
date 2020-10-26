---
title: Data Driven Test with Built-in Data
page_title: Data Driven Test with Built-in Data
description: "Test Studio can use built-in data source for each test. Data drive/ Parameterize a test with Internal data source in Test Studio"
position: 1
---
# Get Started with Data Driven Testing

This approach of testing is useful for a test scenario with certain actions and verifications, which need to be repeated multiple times.

## What Test Scenario Can Be Data Driven?

The easiest answer is that each scenario can be data driven. Test Studio allows you to use data source values for both input fields and verifications. For example, if you need to perform the same actions against an application, but using multiple different users, you can data drive the login input information.

The test scenario described below navigates to the Telerik page and enters different product names in the _Search_ field. If using the common testing approach, you will end up with a test with a separate step to enter the product names.

![common-testing-approach](/img/automated-tests/data-drive-test/local-data-driven-test/common-testing-approach.png)

The same scenario can be fully covered if the three steps related to the search action are reused with the help of data driven testing approach.

## How To Data Drive the Test?

Let's start by adding a new web test into your project.

### Record the Steps to Data Drive

Choose a browser to use and navigate to the Telerik page to start the recording session. Record the actions to click on the _Search_ icon in the top navigation bar, enter 'Test Studio' in the _Search_ field and click on the _Search_ button.

![record-search-actions](/img/automated-tests/data-drive-test/local-data-driven-test/record-search-actions.png)

To ensure that the search was correctly performed, it is recommended to add a step, which waits until the first item of the results list contains the searched product name.

> __Tip__
><br>
><br>
> You can read additional details on wait steps and wait for text from image in particular, in the referred articles.

__add links__ 

Once all necessary steps are added to the test, you can close the browser to finish the recording session.

### Prepare the Data Source

At the bottom of the test steps pane in the project you will see an additional tab named _'Local Data'_. Click this one to switch to the built-in data table.

![switch-to-local-data](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-local-data.png)

The default view of the local data allows you to create a table specifying the number of columns and rows you need. For the current scenario we need a single column and three rows.

![create-data-table](/img/automated-tests/data-drive-test/local-data-driven-test/create-data-table.png)

You can rename the column name to correspond to the data, which it contains - 'productName' for this scenario.

![rename-column](/img/automated-tests/data-drive-test/local-data-driven-test/rename-column.png)

Enter the names of the different products in each row of the column.

![add-data](/img/automated-tests/data-drive-test/local-data-driven-test/add-data.png)

> __Tip__
><br>
><br>
> Read <a href="/features/data-driven-testing/manage-local-data" target="_blank">here how you can modify the built-in data table</a>.

### Bind the Data to the Test Steps

Now that you have the data entered in the built-in table, you can bind the values to the test steps. First, switch back to the steps view by clicking the _Test steps_ tab at the bottom of the test steps pane.

![switch-to-test-steps](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-test-steps.png)

Click on the _Enter text_ step (number 3. for the current scenario) and open the _Properties pane_. The _Bindings_ property is the first in the list. To open the fields for this step, which can be bound to use data values, click the three dots button at the right side of the _Bindings_ property.

![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

> __Note__
><br>
><br>
> Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can be on different location within your project.

The _Enter text_ step allows only its _Text_ field to be data driven and, thus, it is the only one listed. Click on the dropdown next to it to expand the data source columns list. In our scenario there is a single column in the list - the _productName_, so select this one.

![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

To confirm the selection and close the _Properties pane_, click on the _Set_ button.

![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

Apply the same sequence of steps for the wait step added to verify that the search actions is completed successfully. The difference is that the field to bind in the step properties is named _TextToMatch_.

![wait-step-binding](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-binding.png)

> __Note__
><br>
><br>
> All _actions_ steps in Test Studio __scrolls their target element to top of the page__ by default. This is a step property called ___ScrollToVisibleType___, which can be modified from the _Properties_ pane.
><br>
>For the particular case you need to __adjust the mentioned property to scroll the elements to center__, because the Telerik page has a static header and the _Search_ text field and button, otherwise, gets scrolled under it - thus the actual actions cannot be successfully performed.

__add links__ 

### Execute the Data Driven Test

Now that the test is set up to take data from the built-in data table, you can see the two data bound steps showing the column these are connected to. And it can be executed to check what the run looks like - hit the _Execute_ button and choose a browser for the execution.

![execute-data-driven-test](/img/automated-tests/data-drive-test/local-data-driven-test/execute-data-driven-test.png)

Observing the test run, you will see that the 5 steps recorded in the test will be executed three times in a row. The difference for each of these iterations will be the product name entered in the _Search_ field and it corresponds to each of the products listed in the data table.

Once the test run finishes, you will see the quick execution results populated in the _Test Pane_. The results for each iteration are listed separately and you can switch between these from the _Iterations_ dropdown.

![iterations-dropdown](/img/automated-tests/data-drive-test/local-data-driven-test/iterations-dropdown.png)

__add links to other interesting scenarios__ 

add external data source
data drive a step in code
multi level tests


__==============old stufff===================__
Let's create a new, Local Data Driven test. We'll go through five iterations of the test, each with a different search text.

1.Create a new Web Test and click Record.

2.Navigate to www.google.com, enter *Telerik* in the Google search box, and hit the Search button.

3.Click the **Pause** button in the docked recorder toolbar.

![pause][1]

4.Click the **Local Data** button in the bottom of the test or the **Data** tab in Visual Studio.

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

[101]: /img/automated-tests/data-drive-test/local-data-driven-test/common-testing-approach.png
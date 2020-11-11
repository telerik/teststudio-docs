---
title: Data Driven Test with Built-in Data
page_title: Data Driven Test with Built-in Data
description: "Test Studio can use built-in data source for each test. Data drive/ Parameterize a test with Internal data source in Test Studio"
position: 1
---
# Get Started with Data Driven Testing

This approach of testing is useful for a test scenario with certain actions and verifications, which need to be repeated multiple times.

## What Test Scenario Can Be Data Driven?

The easiest answer is that each scenario can be data driven. __Test Studio allows you to use data source values for both input fields and verifications__. For example, if you need to perform the same actions against an application, but using multiple different users, you can __data drive the login input information__.

To demonstrate the capabilities of data driven testing, we will use a test scenario, which navigates to the Telerik page and enters different product names in the _Search_ field and checks the outcome of the results. If using the common testing approach, you will end up with a test, which has a separate step to enter the product names and verify the results for each different product.

![common-testing-approach](/img/automated-tests/data-drive-test/local-data-driven-test/common-testing-approach.png)

This same scenario can be fully covered, if the three steps related to the search action are reused with the help of data driven testing approach.

## How To Data Drive the Test?

Let's start by adding a new web test into your project.

## Record the Steps to Data Drive

Choose a browser to use and navigate to the Telerik page to start the recording session. Record the actions to click on the _Search_ icon in the top navigation bar, enter 'Test Studio' in the _Search_ field and click on the _Search_ button.

![record-search-actions](/img/automated-tests/data-drive-test/local-data-driven-test/record-search-actions.png)

To ensure that the search was correctly performed, it is __recommended to add a step, which waits until the first item of the results list contains the searched product name__.

> __Tip__
><br>
><br>
> You can read additional details on wait steps and wait for text from image in particular, in the referred articles.

__add links__ 

Once all necessary steps are added to the test, you can close the browser to finish the recording session.

## Prepare the Data Source

At the bottom of the test steps pane in the project you will see an additional tab named _'Local Data'_. Click this one to switch to the built-in data table.

![switch-to-local-data](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-local-data.png)

The default view of the local data allows you to __create a table specifying the number of columns and rows__ you need. For the current scenario we need a single column and three rows.

![create-data-table](/img/automated-tests/data-drive-test/local-data-driven-test/create-data-table.png)

You can rename the column name to correspond to the data, which it contains - _'productName'_ for this scenario.

![rename-column](/img/automated-tests/data-drive-test/local-data-driven-test/rename-column.png)

Enter the names of the different products in each row of the column.

![add-data](/img/automated-tests/data-drive-test/local-data-driven-test/add-data.png)

> __Tip__
><br>
><br>
> Read <a href="/features/data-driven-testing/manage-local-data" target="_blank">here how you can modify the built-in data table</a>.

## Bind the Data to the Test Steps

Now that you have the data entered in the built-in table, you can bind the values to the test steps. First, switch back to the steps view by clicking the _Test steps_ tab at the bottom of the test steps pane.

![switch-to-test-steps](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-test-steps.png)

Click on the _Enter text_ step (number 3. for the current scenario) and open the <a href="/features/test-maintenance/test-step-properties" target="_blank">_Step Properties pane_</a>. The ___Bindings___ property is the first in the list. Click the three dots button at its right side to open the fields for this step, which can be bound to use data values.

![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

> __Note__
><br>
><br>
> Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can be on different location within your project.

The _Enter text_ step allows only its ___Text___ field to be data driven and, thus, it is the only one listed. __Click on the drop-down next to it to expand the data source columns list__. In this scenario there is a single column in the list - the _productName_, so select this one.

![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

To __confirm the selection__ and close the _Properties pane_, click on the _Set_ button.

![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

> __Tip__
><br>
><br>
> Read <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">here additional details about how to bind a step to a data source column</a>.

__Apply the same sequence of steps for the wait step__ added to verify that the search actions is completed successfully. The difference is that the field to bind in the step properties is named ___TextToMatch___.

![wait-step-binding](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-binding.png)

> __Note__
><br>
><br>
> All _actions_ steps in Test Studio __scrolls their target element to top of the page__ by default. This is a step property called ___ScrollToVisibleType___, which can be modified from the _Properties_ pane.
><br>
>For the particular case you need to __adjust the mentioned property to scroll the elements to center__, because the Telerik page has a static header and the _Search_ text field and button, otherwise, gets scrolled under it - thus the actual actions cannot be successfully performed.

__add links__ 

## Execute the Data Driven Test and Review the Results

Now that the test is set up to take data from the built-in data table, you can see the two data bound steps showing the column these are connected to. And it can be executed to check what the run looks like - hit the _Execute_ button and choose a browser for the execution.

![execute-data-driven-test](/img/automated-tests/data-drive-test/local-data-driven-test/execute-data-driven-test.png)

Observing the test run, you will see that the 5 steps recorded in the test will be __executed three times in a row__. The __difference for each of these iterations will be the product name entered in the _Search_ field__ and it corresponds to each of the products listed in the data table.

Once the test run finishes, you will see the quick execution results populated in the _Test Pane_. The __results for each iteration are listed separately__ and you can switch between these from the _Iterations_ drop-down.

![iterations-dropdown](/img/automated-tests/data-drive-test/local-data-driven-test/iterations-dropdown.png)

> __Tip__
><br>
><br>
> Find <a href="/automated-tests/data-drive-test/ddt-results#summary-results" target="_blank">here additional details about how to read the results of a data driven test</a>.

__Follow the links below for other data driven scenarios:__

- <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">Data drive a test using external data source</a>
- <a href="/automated-tests/data-drive-test/multi-level-tests" target="_blank">Test as steps used with data driven testing</a>
- <a href="/automated-tests/elements/find-element#data-driven-find-expression" target="_blank">Data drive the find expression of an element in Test Studio</a>
- <a href="/automated-tests/data-drive-test/data-binding-in-code" target="_blank">Usde data source columns in coded steps</a>

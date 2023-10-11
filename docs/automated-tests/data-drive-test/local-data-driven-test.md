---
title: Data Driven Test with Built-in Data
page_title: Data Driven Test with Built-in Data
description: "How to use local data table to data drive a Test Studio test? Test Studio can use built-in data source for each test. Data drive/ Parameterize a test with Internal data source in Test Studio"
position: 1
---
# Get Started with Data Driven Testing

This testing approach is useful for scenarios with certain actions and verifications, which need to be repeated multiple times.

## <strong>What Test Scenario Can Be Data Driven?</strong>

The easiest answer is that each scenario can be data driven. Test Studio allows you to use data source values for both input fields and verifications. For example, if you need to perform the same actions against an application, but by using multiple different users, you can data drive the login input information.

To demonstrate the capabilities of data driven testing, we will use a test scenario, which navigates to the Telerik page, enters different product names in the _Search_ field, and checks the outcome of the results. If you use the common, non data driven testing approach, you will end up with a test that needs three test steps for each individual product that you enter in the search field.

![common-testing-approach](/img/automated-tests/data-drive-test/local-data-driven-test/common-testing-approach.png)

With data driven testing, the three steps related to the search action are reused and you save time and efforts.

## <strong>How To Data Drive the Test?</strong>

Let's start by adding a new web test to your project.

## Record the Steps to Data Drive

Open a browser and navigate to the Telerik page to start the recording session. Record the following actions:

1. Click the __Search__ icon in the top navigation bar.

1. Enter 'Test Studio' in the __Search__ field.

1. Click the __Search__ button.

![record-search-actions](/img/automated-tests/data-drive-test/local-data-driven-test/record-search-actions.png)

To ensure that the search is performed correctly, we recommend to add a step that waits until the first item in the results list contains the searched product name.

> __Tip__
><br>
><br>
> For more details on __wait steps__, see <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">here how to record one</a>
><br>
><br>
> For more details on steps using the __text from an image__, see <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">here how to record such step</a>.

Once all necessary steps are added to the test, __close the browser to finish the recording session__.

## Prepare the Data Source

1. Click the `Local Data` tab located at the bottom of the test pane to switch to the built-in data table.

    ![switch-to-local-data](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-local-data.png)

1. In the `Local Data` tab, specify the number of columns and rows and create a table. For the current scenario we need a single column and three rows.

    ![create-data-table](/img/automated-tests/data-drive-test/local-data-driven-test/create-data-table.png)

1. Rename the column to correspond to the data that it contains - `productName` for this scenario.

    ![rename-column](/img/automated-tests/data-drive-test/local-data-driven-test/rename-column.png)

1. Enter the names of the different products on each row.

    ![add-data](/img/automated-tests/data-drive-test/local-data-driven-test/add-data.png)

> __Tip__
><br>
><br>
> For more information, see <a href="/features/data-driven-testing/manage-local-data" target="_blank">how to modify the built-in data table</a>.

## Bind the Data to the Test Steps

Now that the data is in the built-in table, you can bind the values to the test steps:

1. Switch back to the steps view by clicking the `Test steps` tab at the bottom of the test pane.

    ![switch-to-test-steps](/img/automated-tests/data-drive-test/local-data-driven-test/switch-to-test-steps.png)

1. Select the __Enter text__ step (number 8. for the current scenario) and expand it with double-click. 

    ![expand-step](/img/automated-tests/data-drive-test/local-data-driven-test/expand-step.png)

1. Use the `Data Bind` button to open the `Data binding` dialog. It lists all step's fields which you can use for binding. 

    ![data-bind-dialog](/img/automated-tests/data-drive-test/local-data-driven-test/data-bind-dialog.png)

1. The __Enter text__ step allows only its `Text` field to be data driven so this is the only one listed in the `Binding dialog`. Click on the drop-down next to the  `Text` field and expand the data source columns list. In this scenario the data consists of a single column - the `productName`, so select this one.

    ![choose-binding-column](/img/automated-tests/data-drive-test/local-data-driven-test/choose-binding-column.png)

    > __Tip__
    ><br>
    ><br>
    > See <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">How to bind a step to a data source column</a> for more details.

1. Confirm the binding with the `OK` button. 

    ![confirm-binding](/img/automated-tests/data-drive-test/local-data-driven-test/confirm-binding.png)

1. The step gets updated and hints that is bound to some data. 

    ![bound-step](/img/automated-tests/data-drive-test/local-data-driven-test/bound-step.png)

1. Repeat the same sequence of actions for the __Wait__ step. This step verifies that the search action is completed successfully. The field to bind in the __Wait__ step properties is `ExpectedString`.

    ![wait-step-bound](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-bound.png)

## Execute the Data Driven Test and Review the Results

Now that the test is configured to take data from the built-in data table, you can see the two data-bound steps and the column they are connected to. To run the test, hit the `Execute` button and choose a browser for the execution.

![execute-data-driven-test](/img/automated-tests/data-drive-test/local-data-driven-test/execute-data-driven-test.png)

Observing the test run, you will see that the 5 steps recorded in the test will be executed three times in a row. The difference in each of these iterations will be the product name entered in the __Search__ field. This name corresponds to the products listed in the data table.

Once the test run finishes, you will see the quick execution results populated in the `Test Pane`. The results for each iteration are listed separately, and you can switch between them from the `Iterations` drop-down.

![iterations-dropdown](/img/automated-tests/data-drive-test/local-data-driven-test/iterations-dropdown.png)

> __Tip__
><br>
><br>
> For more information, see <a href="/automated-tests/data-drive-test/ddt-results#summary-results" target="_blank">how to read the results of a data driven test</a>.

## Other data driven scenarios

- <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">Data drive a test using external data source</a>
- <a href="/automated-tests/data-drive-test/multi-level-tests" target="_blank">Test as steps used with data driven testing</a>
- <a href="/automated-tests/elements/find-element#data-driven-find-expression" target="_blank">Data drive the find expression of an element in Test Studio</a>
- <a href="/automated-tests/data-drive-test/data-binding-in-code" target="_blank">Use data source columns in coded steps</a>

## See Also:

* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-data-driven-tests" target="_blank">Step-by-Step: Data-Driven Tests</a>
* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-testing-execution-paths-conditional-tests" target="_blank">Step-by-Step: Testing Execution Paths With Conditional Tests</a>
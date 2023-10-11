---
title: Data Driven Test with External Data
page_title: Data Driven Test with External Data
description: "How to use external data table to data drive a Test Studio test? Bind a test to external data source. Data drive test using an excel sheet. Data drive test using XML file. Data drive test using database. Data drive test using SCV file. "
position: 3
---
# Data Driven Test with External Data

Test Studio allows you to use external data files for data driven testing. This is a suitable option when the data required for the test is more complex and is maintained easier in external type of file or is exported from a different tool.

## How To Data Drive the Test

Let's start by adding a new test in the project and recording the steps to data drive. We can use the <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">same test sample, described for the data driven test with built-in data</a>.

## Record the Steps to Data Drive

Open a browser and navigate to the Telerik page to start the recording session. Record the following actions:

1. Click on the __Search__ icon in the top navigation bar.

1. Enter 'Test Studio' in the __Search__ field.

1. Click on the __Search__ button.

![record-search-actions](/img/automated-tests/data-drive-test/local-data-driven-test/record-search-actions.png)

To ensure that the search was performed correctly, add a step that waits until the first item of the results list contains the searched product name.

> __Tip__
><br>
><br>
> For more details on __wait steps__, see <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">here how to record one</a>
><br>
><br>
> For more details on steps using the __text from an image__, see <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">here how to record such step</a>.

Once you add all necessary steps to the test, __close the browser to finish the recording session__.

## Prepare the Data Source

To demonstrate the usage of external data source, let's prepare a sample Excel file. The data we need for this test is listed in a single row and contains different Telerik product names to search in the site.

> __Note__
><br>
><br>
The first row will be used to refer the column when binding it to the test steps. This is 'productName' in the described scenario.

![external-data](/img/automated-tests/data-drive-test/external-data-driven-test/external-data.png)

## Add the External Data to the Project

To use the external file in a Test Studio project, you need to add a reference to this file in the project. Select the `Project` tab in the Test Studio window and hit the `Add` button from the `Data Source` section in the ribbon.

![add-data-source](/img/automated-tests/data-drive-test/bind-test-data-source/add-data-source.png)

> __Tip__
><br>
><br>
> For more information, see <a href="/features/data-driven-testing/add-data-source" target="_blank">How to add supported data files in the project</a>.

## Bind the External Data Source to Test

Now that you have added a data source definition to your test project, you are ready to bind your test to that data source.

Choose a test from the `Project Explorer` and click the `Bind Test` button from the `Data Source` section in the `Project` ribbon.

![choose-test-to-bind](/img/automated-tests/data-drive-test/bind-test-data-source/choose-test-to-bind.png)

## Confirm Data Binding

When the external data source is configured as desired, click the `OK` button to bind it to the selected test. Now the external file is associated with the test, and you can access the data values in the file and bind them to the steps.

> __Tip__
><br>
><br>
> For more information, see <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">How to bind a test to the external data file</a>.

## Bind the Data to the Test Steps

Once the test has a reference to the data source, you can bind the values to the test steps:

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

Now that the test is set up to take data from the built-in data table, you can see the two data-bound steps and the column they are connected to. To run the test, hit the _Execute_ button and choose a browser for the execution.

![execute-data-driven-test](/img/automated-tests/data-drive-test/local-data-driven-test/execute-data-driven-test.png)

Observing the test run, you will see that the 5 steps recorded in the test will be executed three times in a row. The difference in each of these iterations will be the product name entered in the _Search_ field. This name corresponds to the products listed in the data table.

Once the test run finishes, you will see the quick execution results populated in the _Test Pane_. The results for each iteration are listed separately, and you can switch between them from the _Iterations_ drop-down.

![iterations-dropdown](/img/automated-tests/data-drive-test/local-data-driven-test/iterations-dropdown.png)

> __Tip__
><br>
><br>
> For more information, see <a href="/automated-tests/data-drive-test/ddt-results#summary-results" target="_blank">how to read the results of a data driven test</a>.

## Other data driven scenarios

- <a href="/automated-tests/data-drive-test/multi-level-tests" target="_blank">Test as steps used with data driven testing</a>
- <a href="/automated-tests/elements/find-element#data-driven-find-expression" target="_blank">Data drive the find expression of an element in Test Studio</a>
- <a href="/automated-tests/data-drive-test/data-binding-in-code" target="_blank">Use data source columns in coded steps</a>

## See Also:

* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-data-driven-tests" target="_blank">Step-by-Step: Data-Driven Tests</a>
* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-testing-execution-paths-conditional-tests" target="_blank">Step-by-Step: Testing Execution Paths With Conditional Tests</a>
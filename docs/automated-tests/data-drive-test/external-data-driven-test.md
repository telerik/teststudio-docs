---
title: Data Driven Test with External Data
page_title: Data Driven Test with External Data
description: "Bind a test to external data source. Data drive test using an excel sheet. Data drive test using XML file. Data drive test using database. Data drive test using SCV file. "
position: 3
---
# Data Driven Test with External Data

Test Studio allows you to use external data files for data driven testing. This is a suitable option when the data required for the test is more complex and is maintained easier in external type of file or is exported from a different tool.

## How To Data Drive the Test

Let's start by adding a  new test in the project and proceed with recording the steps to data drive. We can use the <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">same test sample, described for the data driven test with built-in data</a>.

## Record the Steps to Data Drive

Open a browser and navigate to the Telerik page to start the recording session. Record the following actions:

1. Click on the _Search_ icon in the top navigation bar.

1. Enter 'Test Studio' in the _Search_ field.

1. Click on the _Search_ button.

![record-search-actions](/img/automated-tests/data-drive-test/local-data-driven-test/record-search-actions.png)

To ensure that the search was performed correctly, it is recommended to add a step that waits until the first item of the results list contains the searched product name.

> __Tip__
><br>
><br>
> For more details on wait steps, see article 1.
> For more details on wait for text from image, see article 2.

__add links__ 

Once you add all necessary steps to the test, close the browser to finish the recording session.

## Prepare the Data Source

To demonstrate the usage of external data source, let's prepare a sample Excel file. The data we need for this test is listed in a single row and contains different Telerik product names to search in the site.

> __Note__
><br>
><br>
The first row will be used to refer the column when binding it to the test steps. This is _'ProductName'_ in the described scenario.

![external-data](/img/automated-tests/data-drive-test/external-data-driven-test/external-data.png)

## Add the External Data to the Project

To use the external file in a Test Studio project, you need to add a reference to this file in the project. Select the _Project_ tab in the Test Studio window and hit the __Add__ button from the _Data Source_ section in the ribbon.

![add-data-source](/img/automated-tests/data-drive-test/bind-test-data-source/add-data-source.png)

> __Tip__
><br>
><br>
> For more information, see <a href="/features/data-driven-testing/add-data-source" target="_blank">How to add supported data files in the project</a>.

## Bind the External Data Source to Test

Now that you have added a data source definition to your test project, you are ready to bind your test to that data source.

Choose a test from the _Project Explorer_ and click the __Bind Test__ button from the _Data Source_ section in the _Project_ ribbon.

![choose-test-to-bind](/img/automated-tests/data-drive-test/bind-test-data-source/choose-test-to-bind.png)

## Confirm Data Binding

When the external data source is set as desired, click the __OK__ button to bind it to the selected test. Now the external file is associated with the test, and you can access the data values in the file and bind them to the steps.

> __Tip__
><br>
><br>
> For more information, see <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">How to bind a test to the external data file</a>.

## Bind the Data to the Test Steps

Once the test has a reference to the data source, you can bind the values to the test steps:

1. Click on the _Enter text_ step (number 3. for the current scenario) and open the <a href="/features/test-maintenance/test-step-properties" target="_blank">_Step Properties pane_</a>.

1. The ___Bindings___ property is the first in the list. Click the three dots button on the right to open the step fields that you can bind to data.

    ![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

    > __Note__
    ><br>
    ><br>
    > Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can have a different location within your project.

    The _Enter text_ step allows only its _Text_ field to be data driven and, thus, it is the only one listed.

1. Click on the drop-down next to the  ___Text___ field to expand the data source columns list. In this scenario, there is a single column in the list - the _productName_, so select this one.

    ![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

1. Click on the _Set_ button to confirm the selection and close the _Properties pane_.

    ![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

    > __Tip__
    ><br>
    ><br>
    > See <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">How to bind a step to a data source column</a> for more information.

1. Apply the same sequence of steps for the wait step. We add a wait step to verify that the search action is completed successfully. Note that the field that you need to bind in the wait step properties is ___TextToMatch___.

    ![wait-step-binding](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-binding.png)

> __Note__
><br>
><br>
> All _action_ steps in Test Studio scroll their target element to top of the page by default. This is a step property called ___ScrollToVisibleType___, which can be modified from the _Properties_ pane.
><br>
>For the current example, you need to adjust the ___ScrollToVisibleType___ property to scroll the elements to the center because the Telerik page has a static header and the _Search_ text field and button, otherwise, gets scrolled under it - thus the actual actions cannot be successfully performed.

__add links__ 

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
- <a href="/automated-tests/data-drive-test/data-binding-in-code" target="_blank">Usde data source columns in coded steps</a>

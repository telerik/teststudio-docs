---
title: Data Driven Test with External Data
page_title: Data Driven Test with External Data
description: "Bind a test to external data source. Data drive test using an excel sheet. Data drive test using XML file. Data drive test using database. Data drive test using SCV file. "
position: 3
---
# Data Driven Test with External Data

Test Studio allows you to use external data files for data driven testing. This will be a suitable option, when the data to use for a test, is more complex and is maintained easier in external type of file, or is exported from a different tool.

## How To Data Drive the Test

Let's start by adding a  new test in the project and proceed with recording the steps to data drive. We can use the <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">same test sample, described for the data driven test with built-in data</a>.

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

To demonstrate the usage of external data source, let's prepare a sample Excel file. The data we need for this test is listed in a single row and contains different Telerik product names to search in the site.

> __Note__
><br>
><br>
__The first row will be used to refer the column when binding it to the test steps__. This is _'ProductName'_ in the described scenario.

![external-data](/img/automated-tests/data-drive-test/external-data-driven-test/external-data.png)

## Add the External Data to the Project

In order to use the external file in a Test Studio project you need to add a reference for it in the project. Select the _Project_ tab in Test Studio window and hit the __Add__ button from the _Data Source_ section in the ribbon.

![add-data-source](/img/automated-tests/data-drive-test/bind-test-data-source/add-data-source.png)

> __Tip__
><br>
><br>
> Read additional details about the supported data files and <a href="/features/data-driven-testing/add-data-source" target="_blank">how to add these in the project</a>.

## Bind the External Data Source to Test

Now that you have added a data source definition to your test project, you are ready to bind your test to that data source.

Choose a test from the _Project Explorer_ and click the __Bind Test__ button from the _Data Source_ section in the _Project_ ribbon.

![choose-test-to-bind](/img/automated-tests/data-drive-test/bind-test-data-source/choose-test-to-bind.png)

## Confirm Data Binding

When the external data source is set as desired, click the __OK__ button to bind it to the selected test. Now the external file is associated with the test and you can access the data values to bind the steps.

> __Tip__
><br>
><br>
> Read additional details about <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">how to bind a test to the external data file</a>.

## Bind the Data to the Test Steps

Once the data source is referenced to the test, you can bind the values to the test steps.Click on the _Enter text_ step (number 3. for the current scenario) and open the <a href="/features/test-maintenance/test-step-properties" target="_blank">_Step Properties pane_</a>. The _Bindings_ property is the first in the list. Click the three dots button at its right side to open the fields for this step, which can be bound to use data values.

![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

> __Note__
><br>
><br>
> Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can be on different location within your project.

The _Enter text_ step allows only its _Text_ field to be data driven and, thus, it is the only one listed. Click on the dropdown next to it to expand the data source columns list. In our scenario there is a single column in the list - the _productName_, so select this one.

![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

To confirm the selection and close the _Properties pane_, click on the _Set_ button.

![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

> __Tip__
><br>
><br>
> Read <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">here additional details about how to bind a step to a data source column</a>.

Apply the same sequence of steps for the wait step added to verify that the search actions is completed successfully. The difference is that the field to bind in the step properties is named _TextToMatch_.

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

Observing the test run, you will see that the 5 steps recorded in the test will be executed three times in a row. The difference for each of these iterations will be the product name entered in the _Search_ field and it corresponds to each of the products listed in the data table.

Once the test run finishes, you will see the quick execution results populated in the _Test Pane_. The results for each iteration are listed separately and you can switch between these from the _Iterations_ dropdown.

![iterations-dropdown](/img/automated-tests/data-drive-test/local-data-driven-test/iterations-dropdown.png)

> __Tip__
><br>
><br>
> Find <a href="/automated-tests/data-drive-test/ddt-results#summary-results" target="_blank">here additional details about how to read the results of a data driven test</a>.

__add links to other interesting scenarios__ 

data drive a step in code
multi level tests
data driven find expression

[1]: /img/features/data-driven-testing/bind-test-data-source/fig1.png
[2]: /img/features/data-driven-testing/bind-test-data-source/fig2.png
[3]: /img/features/data-driven-testing/bind-test-data-source/fig3.png
[4]: /img/features/data-driven-testing/bind-test-data-source/fig4.png
[5]: /img/features/data-driven-testing/bind-test-data-source/fig5.png
[6]: /img/features/data-driven-testing/bind-test-data-source/fig6.png
[7]: /img/features/data-driven-testing/bind-test-data-source/fig7.png
[8]: /img/features/data-driven-testing/bind-test-data-source/fig8.png

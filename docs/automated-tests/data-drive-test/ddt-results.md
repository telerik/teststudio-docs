---
title: Data Driven Tests Results
page_title: Data Driven Tests Results
description: "Analyze the results of a data driven/ parameterized test in Test Studio quick execution/ single test run. Analyze the results of a data driven/ parameterized test in Test Studio test list/suite run."
position: 5
---
# Data Driven Tests Results

The results from a test bound to a data source present each iteration separately. That way you can easily sort out which is the trouble iteration and modify it as necessary. In this article you can find detailed information about the test results format, generated from a quick run or a test list execution.

## Quick Execution Results

Let's take the example of the <a href="/automated-tests/data-drive-test/local-data-driven-test#record-the-steps-to-data-drive" target="_blank">data driven test with built-in data table</a> as a baseline. Perform a quick run of this test and let's check the generated results.

The example test has five steps as listed below and steps 3. and 5. are bound to the data table values.

1. Navigate to http://www.telerik.com.
1. Navigate to the _Search_ page by clicking the _Magnifier_ icon.
1. Enter product name in the Search field.
1. Trigger the search by clicking the _Search_ button.
1. Wait, until description of the first result contains the searched product, to verify the search is valid.

![Test Steps](/img/automated-tests/data-drive-test/ddt-results/test-steps.png)

> __Note__
><br>
><br>
> The value for the third iteration of the test run is modified to a random string for the purposes of this article.

![Built-in Data modified](/img/automated-tests/data-drive-test/ddt-results/modified-data-table.png)

Click the **Execute** button in the **Test** ribbon. The test steps are executed three times, once for each row in the built-in grid. And the results are listed in the test pane.

### Summary Results

- The __summary shows the result for the selected iteration__.

<table id="no-table">
<tr>
<td>![Test Studio product iteration](/img/automated-tests/data-drive-test/ddt-results/ts-product-iteration.png)</td>
<td>![Random string product iteration](/img/automated-tests/data-drive-test/ddt-results/random-product-iteration.png)</td>
</tr>
<tr>
<td>_Test Studio product iteration_</td>
<td>_Random string product iteration_</td>
</tr>
<table>

- The drop-down menu contains the __list of all iterations, showing the value used__ from the data table.
- Expand the drop-down menu to view the list and choose an iteration to see the results for it.

![Iterations dropdown](/img/automated-tests/data-drive-test/ddt-results/iterations-dropdown.png)

- *Test Studio* and *Kendo* both were part of the text in the first listed search result, thus the verification, if search is valid, passed.
- The random string did not appear in the first listed search result, so the last iteration failed.

<table id="no-table">
<tr>
<td>![Kendo product iteration](/img/automated-tests/data-drive-test/ddt-results/kendo-product-iteration.png)</td>
<td>![Random string product iteration](/img/automated-tests/data-drive-test/ddt-results/random-product-iteration.png)</td>
</tr>
<tr>
<td>_Kendo product iteration_</td>
<td>_Random string product iteration_</td>
</tr>
<table>

### Execution Log Results

To open the complete test execution log, click the **View Log** button.

![Quick Execute Execution Log](/img/automated-tests/data-drive-test/ddt-results/quick-run-log.png)

When reading through the log, you can find the following details:

- The __overall test result__;
- The __result of each iteration__;
- The __data used__ to drive each iteration;
- __Failure information__ for the failed iteration(s);

![View Log](/img/automated-tests/data-drive-test/ddt-results/execution-log.png)

## Test List Results

When a data driven test is part of a test list, the generated results are again __separated for each of the iterations in the test run__. Let's use the same sample test and add it into a test list. Then, run the test list and explore the results.

![view test list results](/img/automated-tests/data-drive-test/ddt-results/test-list-result.png)

The __overall test list result is reported failed__, as it only includes the data driven test modified to fail - one of its iterations is not successful, so only 14 out of 15 steps passed.

![overall test list results](/img/automated-tests/data-drive-test/ddt-results/overall-test-list-result.png)

Use the _Execution Log_ icon to __open the execution log for the current selected test__.

![selected-test-exec-log](/img/automated-tests/data-drive-test/ddt-results/selected-test-exec-log.png)

Double-click the test listed in the result to __drill down to the iterations__. A summary is listed to describe the passed and executed iterations for the test.

![iterations in test list](/img/automated-tests/data-drive-test/ddt-results/iterations-list-test-list.png)

Double-click any of the iterations to __drill down to its results__. In this case select the last failed iteration to review.

![failed iterations in test list](/img/automated-tests/data-drive-test/ddt-results/failed-iteration.png)

Double-click the failing step to open the <a href="/automated-tests/test-results/step-failure-details" target="_blank">___Step Failure Details___</a> window and explore the failure information in further details.

![failed step details in test list](/img/automated-tests/data-drive-test/ddt-results/failed-step-details.png)

Use the _Execution Log_ icon to __open the execution log for the current selected test/iteration__.

![failed-iteration-execution-log](/img/automated-tests/data-drive-test/ddt-results/failed-iteration-execution-log.png)

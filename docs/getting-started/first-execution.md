---
title: Execute Your First Test
page_title: Execute Your First Test
description: "A step by step guide on how you can execute your first recorded test in Test Studio project. Execute a test in Test Studio Project. Start automating with Test Studio."
position: 3
---
# Execute Your First Test

When you have  <a href="/getting-started/first-test" target="_blank">recorded your first test</a>, you need to execute it and check if this needs additional adjustments. In this article you can find useful hints on the below topics.

1. [Quick Test Execution](#quick-test-execution)
2. [Results from Quick Execution](#results-from-quick-execution)
3. [Test List Execution](#test-list-execution)
4. [Test List Results](#test-list-results)

<br><br>
<div><a href="/getting-started/first-test">Back to <strong>Record Your First Test</strong></a><a style="float:right" href="/getting-started/analyze-the-results">Go to <strong>Review The Results and Debug Test Failures</strong></a></div>
<br><br>

## Quick Test Execution

It is time to <a href="/automated-tests/test-execution/quick-execution" target="_blank">execute the recorded test</a> and observe the execution process.

> __Note!__
> <br>
> <br>
> While a test is being executed **do not start another instance of the same browser or any other application** until the run is finished!

1. Once a test scenario is already recorded, click the **Execute** button in the _Test_ ribbon.

    ![Test Studio](/img/getting-started/first-project/fig08.png)

2. In the _Executing_ dialog select Internet Explorer (or any of the other browsers supported for execution) to run the test against and press Enter or click the ***Run*** button.

    ![Select browser](/img/getting-started/first-project/fig09.png)

    > __Note!__
    > <br>
    > <br>
    > This step will be skipped if you have already <a href="/general-information/test-execution/quick-execution" target="_blank">set a preferred browser from the Test ribbon</a>.

3. Test Studio launches the selected browser and executes the steps recorded in the test. The **Execute** button in the _Test_ ribbon is changed to __Abort__ and allows you to stop the test run before it is finished.

    ![Abort Run](/img/getting-started/first-project/fig10.png)

    > __Note!__
    > <br>
    > <br>
    > If you __abort the test execution__ before it is finished, there will be __no results stored__.

## Results from Quick Execution

When the test execution is complete, there will be a summary how many steps were executed and what is the overall result of the run. Each step is indicated as *Passed* or *Failed* with a green or red circle in front of it. <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">Test results are automatically generated</a> and details can be reviewed by clicking on **View Log**.

![View log](/img/getting-started/first-project/fig14.png)

## Test List Execution

Now that you recorded your first test and ensured it is executed successfully, you can <a href="/features/test-lists/create-test-lists" target="_blank">create your first __Test List__</a> and add the existing test in it.

1. Go to the _Test List_ ribbon in Test Studio and click on the __List__ button in the _Add_ section.

    ![Add test list](/img/getting-started/first-project/add-test-list.png)

2. In the _Create a New Test List_ dialog enter a name for the list and add the test in the box on the right side of the window. You can either double click the test to include, or select it and use the _Arrow_ buttons. Confirm the selection with a click on the __Ok__ button.

    ![Create test list](/img/getting-started/first-project/create-test-list.png)

3. The newly created test list appears in the _Test List_ view and you can trigger its execution from the __Run List__ button.

    ![Run test list](/img/getting-started/first-project/run-test-list.png)

## Test List Results

The <a href="/automated-tests/test-list-results/calendar" target="_blank">results from the test list runs</a> are available in the **Results** tab.

![test list results](/img/getting-started/first-project/test-list-results.png)

Find out more about <a href="/automated-tests/test-lists/test-lists-standalone" target="_blank">test lists</a> and the <a href="/automated-tests/test-lists/test-list-execution" target="_blank">execution of test lists</a>.

<div><a href="/getting-started/first-test">Back to <strong>Record Your First Test</strong></a><a style="float:right" href="/getting-started/analyze-the-results">Go to <strong>Review The Results and Debug Test Failures</strong></a></div>
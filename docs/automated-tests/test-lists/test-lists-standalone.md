---
title: Test Lists in Test Studio
page_title: Test Lists in Test Studio
description: "Test Studio Test List. How to create a test list (suite) in Test Studio. Static test list dynamic test list"
position: 0
---
# Test Lists in Test Studio

Once you have a set of tests with different scenarios to test the application you work on, you can combine these into test lists and execute them together in certain sequence.

Test Studio allows you to create static and dynamic test lists. The difference between these is in the tests included in the list. The __Static Test List__ contains a fixed, predetermined list of tests, whereas the __Dynamic Test List__ contains a list of tests that is dynamically generated upon execution, based on the properties set for the tests in project.

======plan to remove these
* A <a href="#static-test-list">Static Test List</a> contains a fixed, predetermined list of tests.
* A <a href="#dynamic-test-list">Dynamic Test List</a> contains a list of tests that is dynamically generated upon execution based on <a href="/features/test-maintenance/test-properties-standalone">test properties</a>.
======plan to remove these

> __Note__
><br>
><br>
> Both _Static_ and _Dynamic_ test lists can execute web, WPF and load tests. If you need to run performance or manual tests in a list, you need to create the respective type of test list. Find <a href="/automated-tests/test-lists/test-lists-type-standalone">here details for manual and performance test list types</a>.

<br>
<br>

## How to Create a Static Test List?

Choose the **Test Lists** tab in the Test Studio project and hit the **List** button in the *Add* section of the ribbon.

![Create List Button][1]

The __'Create a New Test List'__ dialog pops up and lets you choose the _name_ of the list and _tests_ to include. To add a test in the test list, select it on the left side of the dialog, and move it to the right pane by _using the arrow buttons_, or by _double clicking_ on the test name. Once all tests are added, you can click the **OK** button to save the new test list.

![Name the test list and Add tests][2]

> __Tip__
><br>
><br>
> Select multiple tests using the _Shift_ key or _Ctrl_+ Mouse click.

<br>
<br>

### Options to Filter the Listed Tests from Project

- __Filter Tests by Type__

    ![Filter][9]

- __Filter Tests by Name__

    ![Search][10]

- __Use the *Collapse* Button__ to collapse any expanded folders in the listed tests from project. By default when the *'Create a New Test List'* dialog appears, all folders are expanded to see the tests these include.

    ![Collapse][11]

<br>
<br>

## How to Create a Dynamic Test List?

There are __few criteria you can define to filter tests__ upon execution, when creating a dynamic test lists - __test name__, __test path__ and the rest are the __user defined <a href="/features/test-maintenance/test-properties-standalone">test properties__</a> (_Owner, Priority, Custom Property 1, 2, 3_). For the purpose of this example, I have modified two of the user-defined properties - _Owner_ to Telerik and _Priority_ to 1.

![Test properties][6]

To be able to use these properties, you need to choose the **Dynamic List** button in the *Add* section under the **Test Lists** Tab

![Add Dynamic test list][7]

The __'Add Dynamic Test List'__ dialog pops up and lets you choose the _name_ of the list and _create rules_ which tests to include upon execution. __Craft one or more _Rules___ to filter on specific criteria, clicking plus button after each one. The current results are displayed real-time. Once done, click the **OK** button to save the new test list.

![Define Rules which tests to be included in the dynamic list][8]

> __Note__
><br>
><br>
> Each time you click the _Run List_ button, Test Studio dynamically queries the project and executes the tests that meet the criteria of the __Rules__. So, if there are new tests added, which meet the criteria of the rules, these will be included in the test list upon execution.

<br>
<br>

> __Tip__
><br>
><br>
> Follow the link <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">for an in-depth look at Dynamic Test Lists.</a>

<br>
<br>

## How to Execute a Test List?

Once you have created a test list, you can execute it immediately using the __Run List__ button from the _Execution_ section of the ribbon. If you need to schedule the test list run for a future time, or execute it on another machine, you will need to configure the Test Studio Scheduling configuration and then use the __Run List Remotely__ or __Schedule Test List__ buttons.

## See also ##
* <a href="test-lists-type-standalone" target="_blank">Test Lists Type</a>

* <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">A blog for an in-depth look at Dynamic Test Lists</a>

[1]: /img/automated-tests/test-lists/create-test-lists/fig1.png
[2]: /img/automated-tests/test-lists/create-test-lists/fig2.png
[3]: /img/automated-tests/test-lists/create-test-lists/fig3.png
[4]: /img/automated-tests/test-lists/create-test-lists/fig4.png
[5]: /img/automated-tests/test-lists/create-test-lists/fig5.png
[6]: /img/automated-tests/test-lists/create-test-lists/fig6.png
[7]: /img/automated-tests/test-lists/create-test-lists/fig7.png
[8]: /img/automated-tests/test-lists/create-test-lists/fig8.png
[9]: /img/automated-tests/test-lists/create-test-lists/fig2_FilterTestsByType.png
[10]: /img/automated-tests/test-lists/create-test-lists/fig2_searchField.png
[11]: /img/automated-tests/test-lists/create-test-lists/fig2_collapse.png

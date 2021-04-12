---
title: How to Create a Test List 
page_title: How to Create a Test List
description: "Test Studio Test List. How to create a test list (suite) in Test Studio. Static test list dynamic test list"
position: 0
---
# Test Lists in Test Studio

The test lists in Test Studio are a set of tests to be executed in a sequence. You can combine autonomous tests in dynamically generated list and each will be executed in a new browser instance. Or you can pack tests to run in predefined sequence - self-reliant or dependent on the previous tests in the list.

Test Studio provides two options for a test list - a static one, which contains a fixed, predetermined list of tests; and dynamic, which contains a list of tests that is dynamically generated upon execution, based on the properties set for the tests in project. This article describes in details the two kind of test lists:

- <a href="#how-to-create-a-static-test-list">Static Test List</a>
* <a href="#how-to-create-a-dynamic-test-list">Dynamic Test List</a> 

> __Tip__
><br>
><br>
> Both _Static_ and _Dynamic_ test lists can execute __web, responsive web, WPF and load tests__.
><br>
> __Performance__ and __Manual__ tests can be executed in a _Static_ test list only by changing the type of the test list.

<br>
<br>

## How to Create a Static Test List?

Choose the **Test Lists** tab in the Test Studio project and hit the **List** button in the *Add* section of the tools ribbon.

![Create List Button][1]

### Choose Name and Type of the Test List

The __'Create a New Test List'__ dialog pops up and lets you choose the _Name_ of the list, the _Type_ and _Tests_ to include. Changing the _Type_ of the test list determines what tests can be included in it - <a href="/automated-tests/test-lists/test-lists-standalone#automated-type-of-test-list" target="blank">__Automated__</a> for web, responsive web, WPF and load tests, <a href="/automated-tests/test-lists/test-lists-standalone#performance-type-of-test-list" target="blank">__Performance__</a> for running web tests in performance mode, and <a href="/automated-tests/test-lists/test-lists-standalone#manual-type-of-test-list" target="blank">__Manual__</a> for executing manual tests.

![Choose Test List Type][2a]

### Add Tests to the Test List

To add a test in the test list, select it on the left side of the dialog, and move it to the right pane by _using the arrow buttons_, or by _double clicking_ on the test name. Once all tests are added, you can click the **OK** button to save the new test list.

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

There are few test properties you can use to create rules for tests to include in a dynamic test list.

### Test Properties to Filter Tests in Dynamic List

There are __few criteria you can define to filter tests__ upon execution, when creating a dynamic test lists - __test name__, __test path__ and the rest are the __user defined <a href="/features/test-maintenance/test-properties-standalone" target="blank">test properties__</a> (_Owner, Priority, Custom Property 1, 2, 3_). For the purpose of this example, two of the user-defined properties were modified - _Owner_ was set to Telerik and _Priority_ to 1.

![Test properties][6]

> __Note__
><br>
><br>
> The test's ___Priority_ property does not affect the order__ of tests to be executed in a test list. It is a property to be used for filtering rules in the dynamic test lists.

### Create Dynamic Test List

To be able to use these properties, you need to choose the **Dynamic List** button in the *Add* section under the **Test Lists** Tab

![Add Dynamic test list][7]

### Define Rules to Filter the Tests

The __'Add Dynamic Test List'__ dialog pops up and lets you choose the _name_ of the list and _create rules_ which tests to include upon execution. __Craft one or more _Rules___ to filter on specific criteria, clicking plus button after each one. The current results are displayed real-time. Once done, click the **OK** button to save the new test list.

![Define Rules which tests to be included in the dynamic list][8]

> __Note__
><br>
><br>
> Each time you click the _Run List_ button, Test Studio dynamically queries the project and executes the tests that meet the criteria of the __Rules__. So, if there are new tests added, which meet the criteria of the rules, these will be included in the test list upon execution.

<br>
<br>

## How to Execute a Test List?

Once you have created a test list, you can <a href="/automated-tests/test-lists/test-list-execution" target="_blank">execute it</a> immediately using the __Run List__ button from the _Execution_ section of the ribbon. If you need to schedule the test list run for a future time, or execute it on another machine, you will need to configure the Test Studio Scheduling configuration and then use the __Run List Remotely__ or __Schedule Test List__ buttons.


[1]: /img/features/test-lists/create-test-list/fig1.png
[2]: /img/features/test-lists/create-test-list/fig2.png
[2a]: /img/features/test-lists/create-test-list/fig2a.png
[3]: /img/features/test-lists/create-test-list/fig3.png
[4]: /img/features/test-lists/create-test-list/fig4.png
[5]: /img/features/test-lists/create-test-list/fig5.png
[6]: /img/features/test-lists/create-test-list/fig6.png
[7]: /img/features/test-lists/create-test-list/fig7.png
[8]: /img/features/test-lists/create-test-list/fig8.png
[9]: /img/features/test-lists/create-test-list/fig2_FilterTestsByType.png
[10]: /img/features/test-lists/create-test-list/fig2_searchField.png
[11]: /img/features/test-lists/create-test-list/fig2_collapse.png

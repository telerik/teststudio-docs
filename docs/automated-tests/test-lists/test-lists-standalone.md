---
title: Test Lists
page_title: Test Lists in Test Studio
description: "Test Studio Test List. How to create a test list (suite) in Test Studio. Static test list dynamic test list"
position: 0
---
# Test Lists in Test Studio

The test lists in Test Studio are a set of tests to be executed in a sequence. You can combine autonomous tests in dynamically generated list and each will be executed in a new browser instance. Or you can pack tests to run in predefined sequence - self-reliant or dependent on the previous tests in the list.

Test Studio provides two options for a test list - a static one, which contains a fixed, predetermined list of tests; and dynamic, which contains a list of tests that is dynamically generated upon execution, based on the properties set for the tests in project. This article describes in details the usage of the two kinds of test lists:

- <a href="#static-test-lists">Static Test List</a>
* <a href="#dynamic-test-lists">Dynamic Test List</a> 

## <strong>Static Test Lists</strong>

In a static test list you can add **web, responsive web, WPF, load tests or combination of these**, **manual** and **performance** tests. There are three types of test lists to cover the different types of tests - automated, manual and performance. The type of test list is defined when <a href="/features/test-lists/create-test-lists#choose-name-and-type-of-the-test-list" target="_blank">creating the test list</a>.

![Choose Test List Type][1]

> __Note__
><br>
><br>
> The tests in a static test list will be **executed in the order displayed, when adding them**. You can rearrange the order of the tests by editing the test list.

### Automated Type of Test List

The **Automated** test list type is the standard to execute one or more **web**, **responsive web**, **load** or **WPF** tests. When creating this type of list, you can only choose the listed kind of tests to include (the manual tests are greyed out).

### Performance Type of Test List

The **Performance** test list type allows you to execute **performance runs for one or more web tests**. This type of list can include only web tests (the rest of the tests are greyed out). Next to each test added in the list, you have a __Configure...__ button to apply the <a href="/features/testing-types/performance-testing/gather-perfomance-data" target="_blank">settings</a> for the performance run.

![Configure][4]

### Manual Type of Test List

The **Manual** type of list allows you to add only **manual** tests and execute them together (the rest of the tests are greyed out). Run the manual tests sequentially or toggle back and forth between them using the **Previous** and **Next** buttons at the bottom.

<table id="no-table">
	<tr>
		<td>![Previous][2]</td>
		<td>![Next][3]</td>
	</tr>
<table>

## <strong>Dynamic Test Lists</strong>

The dynamic test list can be only automated type and as such, it can execute one or more **web**, **responsive web**, **load** or **WPF** tests, or a combination of these. When <a href="/features/test-lists/create-test-lists#how-to-create-a-dynamic-test-list" target="_blank">creating the dynamic test list</a> there are a bunch of <a href="/features/test-maintenance/test-properties-standalone" target="_blank">__test properties__</a>, which you can use as criteria for filtering the tests from project - __test name__, __test path__ and the, so called, __user defined properties__ - __Owner, Priority, Custom Property 1, 2, 3__.

![Test properties][6]

These criteria can be used when <a href="/features/test-lists/create-test-lists#create-dynamic-test-list" target="_blank">defining the __Rules__</a>, which tests to be included in the dynamic test list.

![Define Rules which tests to be included in the dynamic list][8]

> __Note__
><br>
><br>
> Each time you trigger a dynamic list execution, Test Studio queries the project and executes the tests, that __meet the criteria of the _Rules___. Thus, if there are new tests added after the test list creation, and these meet the criteria of the rules, they will be included in the test list upon execution.

## See also ##

* <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">An in-depth look at Dynamic Test Lists</a>

[1]: /img/automated-tests/test-lists/test-lists-types/fig1.png
[2]: /img/automated-tests/test-lists/test-lists-types/fig2.png
[3]: /img/automated-tests/test-lists/test-lists-types/fig3.png
[4]: /img/automated-tests/test-lists/test-lists-types/fig4.png
[5]: /img/automated-tests/test-lists/test-lists-types/fig5.png
[6]: /img/automated-tests/test-lists/test-lists-types/fig6.png
[7]: /img/automated-tests/test-lists/test-lists-types/fig7.png
[8]: /img/automated-tests/test-lists/test-lists-types/fig8.png
[9]: /img/automated-tests/test-lists/test-lists-types/fig2_FilterTestsByType.png
[10]: /img/automated-tests/test-lists/test-lists-types/fig2_searchField.png
[11]: /img/automated-tests/test-lists/test-lists-types/fig2_collapse.png

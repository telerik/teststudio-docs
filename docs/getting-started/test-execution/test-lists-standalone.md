---
title: Test Lists (Standalone)
page_title: Test Lists (Standalone)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-execution/standalone-test-lists.aspx, /user-guide/test-execution/standalone-test-lists
position: 1
---
# Test Lists (Standalone) #

In the Standalone version you can execute one or more tests through a Test List. There are two types of Test Lists: **Static** and **Dynamic**.

* A <a href="#static-test-list">Static Test List</a> contains a fixed, predetermined list of tests.
* A <a href="#dynamic-test-list">Dynamic Test List</a> contains a list of tests that is dynamically generated upon execution based on test properties.

## Static Test List ##

1.&nbsp; Click the **Test Lists** tab.

2.&nbsp; Click **List** in the **Add** ribbon.

![List][1]

3.&nbsp; Name the Test List.

4.&nbsp; Add the test(s) to the list from left to right either using the arrow buttons or double click the test to include in test list. 

![Add][2]

5.&nbsp; The available tests in the project to be included in a Test List could be filtered by their type. 

![Filter][9]

Available is also a search field to search scripts by their name. 

![Search][10]

As of release **R1 2018** there is a *Collapse button* for your convenience. It will collapse all expanded tests and folders.

![Collapse][11]

6.&nbsp; Click **OK** to save the new Test List.

7.&nbsp; Click **Run List** in the **Execution** ribbon.

![Run][3]

*Select multiple Test Lists using the Shift key or Ctrl + Click, then click Run List to execute those lists in their order of selection.*

8.&nbsp; The Test Studio Test Runner launches first in a command prompt window. This calls each test in the list.

![Runner][4]

9.&nbsp; A browser window or WPF app opens and each test executes in sequence. Upon completion, the **Results** tab opens.

![Results][5]

10.&nbsp; To view the test results, double click the test result entry in the Timeline view (*MyTestList* in this example).

## Dynamic Test List ##

1.&nbsp; Click the **Project** tab. Select a test and refer to the Test Details pane on the right. Below I have set Owner to *Telerik* and Priority to 1.

![Test properties][6]

2.&nbsp; Click the **Test Lists** Tab

3.&nbsp; Click **Dynamic List** in the **Add** ribbon.

![Add][7]

4.&nbsp; Name the Test List.

5.&nbsp; Craft one or more Rules to filter on specific criteria, clicking plus button after each one. The current results are displayed real-time.

![Rules][8]

6.&nbsp; Click **OK** to save the new Test List.

> Each time you click Run List in the Execution ribbon, Test Studio dynamically queries the project and executes the tests that meet the criteria of the Rules.

## See also ##
* <a href="test-lists-type-standalone" target="_blank">Test Lists Type</a>

* <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">Blog post</a> for an in-depth look at Dynamic Test Lists.

[1]: /img/getting-started/test-execution/test-lists-standalone/fig1.png
[2]: /img/getting-started/test-execution/test-lists-standalone/fig2.png
[3]: /img/getting-started/test-execution/test-lists-standalone/fig3.png
[4]: /img/getting-started/test-execution/test-lists-standalone/fig4.png
[5]: /img/getting-started/test-execution/test-lists-standalone/fig5.png
[6]: /img/getting-started/test-execution/test-lists-standalone/fig6.png
[7]: /img/getting-started/test-execution/test-lists-standalone/fig7.png
[8]: /img/getting-started/test-execution/test-lists-standalone/fig8.png
[9]: /img/getting-started/test-execution/test-lists-standalone/fig2_FilterTestsByType.png
[10]: /img/getting-started/test-execution/test-lists-standalone/fig2_searchField.png
[11]: /img/getting-started/test-execution/test-lists-standalone/fig2_collapse.png

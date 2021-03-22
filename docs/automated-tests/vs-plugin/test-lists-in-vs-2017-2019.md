---
title: Test Lists in Visual Studio 2017 and 2019
page_title: Test Lists in Visual Studio 2017 and 2019
description: "Test Lists in Visual Studio. How to create a test list (suite) in Visual Studio. Static test list dynamic test list"
position: 3
---
# Test Lists in Visual Studio 2017 and 2019 #

Visual Studio 2017 and 2019 allow the implementation and usage of the Test Studio test lists in the plugin. This article describes the specifics of how to create and maintain the test lists in the project in Visual Studio.

There test lists can be two types as well - **Static** and **Dynamic**.

* A <a href="#add-test-files-to-static-test-list">Static Test List</a> contains a fixed, predetermined list of tests.
* A <a href="#add-test-files-to-dynamic-test-list">Dynamic Test List</a> contains a list of tests that is dynamically generated upon execution based on <a href="/features/test-maintenance/test-properties-vs">test properties</a>.

> __Note!__ Test lists in Visual Studio can only execute web or WPF functional tests.

## Create a Test List File in Visual Studio ##

A test list file has the extension ___*.aiilist___ and can be added in a Visual Studio project under a predefined folder named ___TestLists___ - this folder exists in each new project.

![TestLists folder in Solution explorer][1]

Right click on the ___TestLists___ folder and choose __Test Studio Test List__ or __Test Studio Dynamic Test List__ from the _Add_ section sub-menu.

![Add a test list file][2]

Choose a meaningful name for the test list and ensure the correct item from the item list is selected. Confirm the test list creation with the _Add_ button.

![Name and create the test list file][3]

The test list file will be listed under the ___TestLists___ folder.

![Test list file listed under TestLists folder][4]

Build the solution (press F6) and all test list files will appear in the Test Explorer available for execution.

![Test list files listed in Test Explorer][5]

### Add a Test List in Newly Created Project ###

Ensure you are using Test Studio with minimum version 2019.3 and create a new Test Studio project in Visual Studio 2017 or 2019. In the Solution Explorer you can add test list files under the folder named ___TestLists___.

### Add a Test List in an Existing Project ###

Once you upgrade Test Studio to minimum version 2019.3 and open an existing project, you will be prompted with a message, that the project needs to be upgraded as well. Once the upgrade is done and the project is loaded, you will need to include the ___TestLists___ folder in the solution.

<br>

To do that select the Test Studio project in the __Solution Explorer__ and click the ___Show All Files___ button.

![Show All Files for the TS project][6]

Now all files from the project root folder will be listed in the __Solution Explorer__. Right click the ___TestLists___ folder and select ___Include In Project___.

![Include TestLists folder in TS project][7]

Again click the ___Show All Files___ button to hide the other files. Save and reopen the solution to apply the changes. Now the ___TestLists___ folder can be used to add test list files in it.

## Add Test Files to Static Test List ##

Once a test list file is added into the ___TestLists___ folder, double click it to choose the test files to add in it.

![Add test to static list][8]

Save the test list file to apply the changes and execute the test list from the ___Test Explorer___ in Visual Studio.

## Add Test Files to Dynamic Test List ##

Once a test list file is added into the ___TestLists___ folder, double click it to craft the rules to filter, upon specific criteria, the test files to add.

![Add test to dynamic list][9]

The rules can be built upon the specific <a href="/features/test-maintenance/test-properties-vs" target="_blank">test properties</a>..

![Available properties to create rules][10]

> __Note!__ Each time you run a dynamic test list, the project is being queried and only the tests, which meet the criteria of the rules, are executed.

__See also:__ You can find further interesting details in the following <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">in-depth look at Dynamic Test Lists</a>.

## Test List Settings in Visual Studio ##

To change any of the <a href="/general-information/test-execution/test-list-settings" target="_blank">Test List settings</a> in Visual Studio, use the gear icon in the upper right corner in each test list.

![Test List Settings][11]

## Execute Test List Files in Visual Studio ##

To execute the designed test lists in Visual Studio, you can use the different <a href="/general-information/test-execution/vs-test-explorer#run-tests-and-test-lists-in-test-explorer" target="_blank">Run options in Visual Studio Test Explorer</a>.

[1]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig1.png
[2]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig2.png
[3]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig3.png
[4]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig4.png
[5]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig5.png
[6]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig6.png
[7]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig7.png
[8]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig8.png
[9]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig9.png
[10]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig10.png
[11]: /img/general-information/test-execution/test-lists-in-vs-2017-2019/fig11.png

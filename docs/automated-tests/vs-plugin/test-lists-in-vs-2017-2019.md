---
title: Test Lists in Visual Studio 2019 and Later
page_title: Test Lists in Visual Studio 2019 and Later
description: "Test Studio Test Lists in Visual Studio - supported for Visual Studio  2019 and 2022. How to create a list (suite) of Test Studio tests in Visual Studio project. Can I execute static or dynamic Test Studio test list from Visual Studio project."
position: 3
---
# Test Lists in Visual Studio 2019 and Later

Visual Studio 2019 and later allows you to add and run the <a href="/automated-tests/test-lists/test-lists-standalone">Test Studio test lists</a> in the context of the Visual Studio project. Depending on the requirements there are two options of test lists, which you can add in the Visual Studio project - **Static** and **Dynamic**.

In this article you can find useful information on the below topics:

- [Test Lists in Visual Studio 2019 and Later](#test-lists-in-visual-studio-2019-and-later)
  - [Create a Test List in Visual Studio Project](#create-a-test-list-in-visual-studio-project)
  - [Add a Test List in an Existing Project](#add-a-test-list-in-an-existing-project)
  - [Add Test Files to Static Test List](#add-test-files-to-static-test-list)
  - [Add Test Files to Dynamic Test List](#add-test-files-to-dynamic-test-list)
  - [See Also](#see-also)
  - [Test List Settings in Visual Studio](#test-list-settings-in-visual-studio)
  - [Execute Test List Files in Visual Studio](#execute-test-list-files-in-visual-studio)

> __Note!__
><br>
><br>
> Test lists in Visual Studio __only execute functional tests__ e.g. WPF, Desktop and web tests.

## Create a Test List in Visual Studio Project

A Test Studio test list file has the extension __*.aiilist__ and can be added in a Visual Studio project under a predefined folder named __TestLists__ - this folder exists by default in each new project.

![TestLists folder in Solution explorer][1]

Right click on the __TestLists__ folder and choose from the _Add_ section sub-menu any of the options __Test Studio Test List__ or __Test Studio Dynamic Test List__ .

![Add a test list file][2]

Set a name for the test list and double check if the correct test list item from the list is selected. Confirm the test list creation by clicking the _Add_ button.

![Name and create the test list file][3]

The newly created test list is listed under the __TestLists__ folder.

![Test list file listed under TestLists folder][4]

Build the solution (press F6) and all test list files will appear in the Test Explorer available for execution.

![Test list files listed in Test Explorer][5]

## Add a Test List in an Existing Project

The Test Studio test lists in Visual Studio are implemented with Test Studio version 2019.3.xx. Thus, any project created with Test Studio prior this version requires some adjustment to enable the usage of test lists - the __TestLists__ folder is not included in the solution for older projects and needs to be added manually.

Open the Test Studio project and choose the option __Show All Files__ in the __Solution Explorer__.

![Show All Files for the TS project][6]

With this all items from the project root folder will be listed in the __Solution Explorer__. Select the __TestLists__ folder and choose the  __Include In Project__ option from the right click context menu.

![Include TestLists folder in TS project][7]

Click the __Show All Files__ button again to toggle the view and __hide the other files__ and folders. Save and reopen the solution to apply the changes. Now the __TestLists__ folder can be used to add test list files in it as described [above](#create-a-test-list-in-visual-studio-project).

## Add Test Files to Static Test List

Once a static test list file is added into the __TestLists__ folder, double click this to open it. In this view you can choose the test files to include in the test list. All tests in the project are listed on the left side of the pane - you can use the arrows to move a file on the right side to include it in the test list.

![Add test to static list][8]

Save the test list file to keep the changes. The test list can be [executed](#execute-test-list-files-in-visual-studio) from the __Test Explorer__ in Visual Studio.

## Add Test Files to Dynamic Test List

Once a dynamic test list file is added into the __TestLists__ folder, double click this to open it and craft the rules to filter the test files to add in the list.

![Add test to dynamic list][9]

This type of test list lets you choose the tests to include dynamically based on some of the <a href="/features/test-maintenance/test-properties-vs" target="_blank">test properties</a>. These, which you can rely upon, are the user-defined properties - Name, Owner, Path, Priority and the custom properties.

![Available properties to create rules][10]

Save the test list file to keep the changes. The test list can be [executed](#execute-test-list-files-in-visual-studio) from the __Test Explorer__ in Visual Studio.

> __Note!__
><br>
><br>
> Each time a dynamic test list run is initiated, all tests in the project get queried and only these, which meet the criteria of the rules, are included in the test list and executed.
><br>
><br>
> __Tip__
><br>
><br>
> You can find further interesting details in the following <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">in-depth look at Dynamic Test Lists</a>.

## See Also

* <a href="http://blogs.telerik.com/automated-testing-tools/posts/13-09-23/power-of-dynamic-test-lists" target="_blank">In-depth look at Dynamic Test Lists</a>.

## Test List Settings in Visual Studio

<a href="/general-information/test-execution/test-list-settings" target="_blank">Test list settings</a> can be customized to fit the specific environment and customer requirements. In Visual Studio you can access these through the _gear_ icon in the upper right corner when a test list file is opened.

![Test List Settings][11]

## Execute Test List Files in Visual Studio

To execute the test lists in Visual Studio, you can use the different <a href="/general-information/test-execution/vs-test-explorer#run-tests-and-test-lists-in-test-explorer" target="_blank">Run options in Visual Studio Test Explorer</a>.

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

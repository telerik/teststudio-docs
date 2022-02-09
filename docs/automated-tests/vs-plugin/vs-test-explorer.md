---
title: Visual Studio Test Explorer
page_title: Visual Studio Test Explorer
description: "Running Test Studio Tests in Visual Studio Test Explorer. Test Explorer lists the Test Studio tests within the currently opened project. How to change the settings to be used when running tests from the Test Explorer?"
position: 4
---
# Test Explorer in Visual Studio 

The <a href="https://docs.microsoft.com/en-us/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019&redirectedfrom=MSDN" target="_blank">Test Explorer</a> in Visual Studio discovers and runs unit tests from Visual Studio or third-party test projects, including Test Studio tests and test lists.

In this article you can find useful details for running the Test Studio tests from the Test Explorer:

* [Open Test Explorer and view Test Studio tests and test lists](#view-tests-and-test-lists-in-test-explorer)
* [Group Test Studio tests and test lists in Test Explorer](#group-tests-and-test-lists-in-test-explorer)
* [Run Test Studio tests and test lists in Test Explorer](#run-tests-and-test-lists-in-test-explorer)
* [Test Studio settings for Test Explorer test runs](#test-studio-settings-for-test-explorer-test-runs)

## View Tests and Test Lists in Test Explorer

If the __Test Explorer__ pane is not opened in your Visual Studio, you can access this as follows:

- in Visual Studio 2015 and 2017 - **Test -> Windows -> Test Explorer**;
- in Visual Studio 2019 and later - **Test -> Test Explorer**;
- or use keyboard shortcut _Ctrl + E, T_.

![Test menu to open Test Explorer][1]

The Test Studio tests and test lists are listed in the __Test Explorer__ automatically when the project is opened. To reflect any recent changes in the tests and test lists, you need to __build/rebuild the Visual Studio project__.

![Test Explorer][2]

## Group Tests and Test Lists in Test Explorer

You can use Test Explorer to group tests into categories, filter the list of tests, and create, save, and run playlists of tests. There are few different options to group the test files and what makes sense in the context of Test Studio test project is to use __custom grouping starting with either _Namespace_ or _Project_, and use _Class_ and _State_ as sub-filters__ in the desired order.

![Group Tests and Test lists][3]

## Run Tests and Test Lists in Test Explorer

To execute the test files from __Test Explorer__, use the **Run...** buttons and their available options.

> __Note!__
><br>
><br>
> To reflect any recent changes in the listed tests in Test Explorer, you need to __build or rebuild the project__ before starting the test run.

![Run Tests and Test lists][4]

## Test Studio Settings for Test Explorer Test Runs

The execution of Test Studio tests from the Test Explorer uses a set of default settings. To be able to modify these, you need to __add a <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">*.testsettings file in the solution</a>__. This file allows you to apply changes in the test run options like timeouts, executing browser, etc.

> __Note!__
><br>
><br>
> Test Studio __test list files are using <a href="/general-information/test-execution/test-lists-in-vs-2017-2019#test-list-settings-in-visual-studio" target="_blank">their own settings</a>__ when executed from Test Explorer.

[1]: /img/general-information/test-execution/vs-test-explorer/fig1.png
[2]: /img/general-information/test-execution/vs-test-explorer/fig2.png
[3]: /img/general-information/test-execution/vs-test-explorer/fig3.png
[4]: /img/general-information/test-execution/vs-test-explorer/fig4.png

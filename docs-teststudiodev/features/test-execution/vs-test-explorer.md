---
title: Visual Studio Test Explorer 
page_title: Visual Studio Test Explorer | Test Studio Dev Documentation
description: Test Studio Dev tests are recognized by VS Test Explorer and can be executed from its context. Run Test Studio Dev tests via the Test Explorer in Visual Studio
position: 1
---
# Visual Studio Test Explorer #

The <a href="http://msdn.microsoft.com/en-us/library/hh270865.aspx" target="_blank">Test Explorer</a> in Visual Studio discovers and runs tests, including Test Studio Dev tests and <a href="/features/test-execution/test-lists-in-vs-2017-2019" target="_blank">test lists</a>.

## View Tests and Test Lists in Test Explorer ##

If the __Test Explorer__ pane is not opened in your Visual Studio, you can access this as follows:

- in Visual Studio 2015 and 2017 - **Test -> Windows -> Test Explorer**;
- in Visual Studio 2019 and later - **Test -> Test Explorer**;
- or use keyboard shortcut _Ctrl + E, T_.

![Test tab][1]

The Test Studio Dev tests and test lists are listed in the __Test Explorer__ automatically when the project is opened. To reflect any recent changes in the tests and test lists, you need to __build/rebuild the Visual Studio project__.

![Test Explorer][2]

## Group Tests and Test Lists in Test Explorer ##

You can use Test Explorer to group tests into categories, filter the list of tests, and create, save, and run playlists of tests. There are few different options to group the test files and what makes sense in the context of Test Studio test project is to use __custom grouping starting with either _Namespace_ or _Project_, and use _Class_ and _State_ as sub-filters__ in the desired order.

![Group Tests and Test lists][3]

## Run Tests and Test Lists in Test Explorer ##

To execute the test files from __Test Explorer__, use the **Run...** buttons and their available options.

> __Note!__
><br>
><br>
> To reflect any recent changes in the listed tests in Test Explorer, you need to __build or rebuild the project__ before starting the test run.

![Run Tests and Test lists][4]

Thus a test, executed using the <a href="/features/test-execution/quick-execution" target="_blank">Quick Execution</a> option, remains under __Not Run__ category for the Test Explorer, until the test run is triggered from it.

## Test Studio Settings for Test Explorer Test Runs

The execution of Test Studio tests from the Test Explorer uses a set of default settings. To be able to modify these, you need to __add a <a href="/advanced-topics/project-configuration/test-explorer-settings" target="_blank">*.testsettings file in the solution__</a>. This file allows you to apply changes in the test run options like timeouts, executing browser, etc.

> __Note!__
><br>
><br>
> Test Studio Dev __test list files are using <a href="/features/test-execution/test-list-settings" target="_blank">their own settings</a>__ when executed from Test Explorer.

[1]: images/vs-test-explorer/fig1.png
[2]: images/vs-test-explorer/fig2.png
[3]: images/vs-test-explorer/fig3.png
[4]: images/vs-test-explorer/fig4.png

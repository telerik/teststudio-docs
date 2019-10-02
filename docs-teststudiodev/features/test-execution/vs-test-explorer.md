---
title: Visual Studio Test Explorer 
page_title: Visual Studio Test Explorer | Test Studio Dev Documentation
description: Test Studio Dev tests are recognized by VS Test Explorer and could be executed by it. Run Test Studio Dev tests via the Test Explorer in Visual Studio
position: 1
---
# Visual Studio Test Explorer #

The <a href="http://msdn.microsoft.com/en-us/library/hh270865.aspx" target="_blank">Test Explorer</a> in Visual Studio discovers and runs tests, including Test Studio Dev tests and <a href="/features/test-execution/test-lists-in-vs-2017-2019" target="_blank">test lists</a>.

## View Tests and Test Lists in Test Explorer ##

To open Test Explorer in Visual Studio, choose **Test -> Windows -> Test Explorer**

![Test tab][1]

Once the project is built, Test Explorer lists the __Test Studio Dev__ tests and test lists within the currently opened solution with their execution status in the Test Explorer. Thus a test, executed with the Quick Execution Test Runner, will still remain _Not Run_ in the Test Explorer, until a run is triggered from it.

![Test Explorer][2]

>__Note!__ Ensure the __project is re-built before initiating a run from the VS Test Explorer__. Any recent changes will not be reflected otherwise.

## Group Tests and Test Lists in Test Explorer ##

_Test Explorer_ provides few different options to group the listed files. What makes sense in the context of Test Studio Dev tests is to use custom grouping starting with either _Namespace_ or _Project_, and then use as sub-filters _Class_ and _State_ in the desired order.

![Group Tests and Test lists][3]

## Run Tests and Test Lists in Test Explorer ##

To execute the test files in _Test Explorer_, use the **Run...** buttons and their different options.

>__Note!__ Ensure the __project is re-built before initiating a run from the VS Test Explorer__. Any recent changes will not be reflected otherwise.

![Run Tests and Test lists][4]

> __Note!__ When executing test files from Test Explorer <a href="/features/project-settings/overview" target="_blank">Test Studio Dev project settings</a> are not applied.
<br>
<br>
To use the default Test Studio settings, or modify these as per the current requirements, a <a href="/advanced-topics/project-configuration/test-explorer-settings" target="_blank">project settings file need to be added</a> and applied for the test execution from Test Explorer.
<br>
<br>
Test list files are using <a href="/features/test-execution/test-list-settings" target="_blank">their own settings</a> when executed from Test Explorer.

[1]: images/vs-test-explorer/fig1.png
[2]: images/vs-test-explorer/fig2.png
[3]: images/vs-test-explorer/fig3.png
[4]: images/vs-test-explorer/fig4.png

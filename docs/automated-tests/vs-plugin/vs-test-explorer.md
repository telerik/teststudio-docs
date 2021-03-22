---
title: Visual Studio Test Explorer
page_title: Visual Studio Test Explorer
description: "Test Studio Visual Studio Test Explorer. The Test Explorer lists the Test Studio tests within the currently opened solution. Add Test Studio test settings and apply these for the Test Explorer execution"
position: 4
---
# Visual Studio Test Explorer #

As of Update 1, Visual Studio 2012 deprecates <a href="http://msdn.microsoft.com/en-us/library/dd293547.aspx" target="_blank">Test View</a> and <a href="http://msdn.microsoft.com/en-us/library/dd286595.aspx" target="_blank">Test Lists</a>. The <a href="https://docs.microsoft.com/en-us/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019&redirectedfrom=MSDN" target="_blank">Test Explorer</a> discovers and runs unit tests, including Test Studio tests and test lists.

## View Tests and Test Lists in Test Explorer ##

To open Test Explorer in Visual Studio, choose **Test -> Windows -> Test Explorer**.

![Test tab][1]

Once the project is built (press F6), the Test Studio tests and test lists within the currently opened solution are listed in the _Test Explorer_.

![Test Explorer][2]

## Group Tests and Test Lists in Test Explorer ##

_Test Explorer_ provides few different options to group the listed files. What makes sense in the context of Test Studio tests is to use custom grouping starting with either _Namespace_ or _Project_, and then use as sub-filters _Class_ and _State_ in the desired order.

![Group Tests and Test lists][3]

## Run Tests and Test Lists in Test Explorer ##

To execute the test files in _Test Explorer_, use the **Run...** buttons and their different options.

>__Note!__ Ensure the __project is re-built before initiating a run from the VS Test Explorer__. Any recent changes will not be reflected otherwise.

![Run Tests and Test lists][4]

> __Note!__ When executing test files from Test Explorer <a href="/features/project-settings/overview" target="_blank">Test Studio project settings</a> are not applied.
<br>
<br>
To use the default Test Studio settings, or modify these as per the current requirements, a <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">project settings file need to be added</a> and applied for the test execution from Test Explorer.
<br>
<br>
Test list files are using <a href="/general-information/test-execution/test-lists-in-vs-2017-2019#test-list-settings-in-visual-studio" target="_blank">their own settings</a> when executed from Test Explorer.

[1]: /img/general-information/test-execution/vs-test-explorer/fig1.png
[2]: /img/general-information/test-execution/vs-test-explorer/fig2.png
[3]: /img/general-information/test-execution/vs-test-explorer/fig3.png
[4]: /img/general-information/test-execution/vs-test-explorer/fig4.png

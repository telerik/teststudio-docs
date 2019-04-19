---
title: Compilation Exceptions when Executing Remotely
page_title: Compilation Exceptions when Executing Remotely
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Compilation Exceptions when Executing Remotely 

## PROBLEM

My test list executes exception free when it is executed from the project location. If I schedule it to be executed remotely there are compilation exceptions in the execution log similar to this one:

`Compile failed: c:\Users\someuser\AppData\Local\Temp\8\Projects\2fa80212-43cb-4b99-882c-e69f4d1936d2\TestRemoteElemMissing\RunTest.tstest.cs(53,19) : error CS1061: 'TestRemoteElemMissing.Pages' does not contain a definition for 'Google' and no extension method 'Google' accepting a first argument of type 'TestRemoteElemMissing.Pages' could be found (are you missing a using directive or an assembly reference?)`

Such behavior could appear if executing a test list scheduled or remotely. By design when a test list is being run remotely/scheduled only tests listed for execution in the current list are deployed on the execution machines. While maintaining the project and creating tests elements will be recorded in tests (please see *Test 1* on the image below to illustrate the example).

![Defined Element][1]

Though the same element could be reached from another test for example - in a *RunTest* coded step (on the image below).

![Used in Different Test][2]

When locally executed on the machine which hosts the project there will be no compilation errors since the complete project is available and compiled from its root folder prior execution. Though if only the test *RunTest* is placed in a test list for remote/scheduled execution the given above compilation exception would occur.

## SOLUTION 1

To refer an element trough the Pages file is not a recommended practice as you could face similar difficulties. An approach to avoid the above described issue could be to identify the element in code using <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">the identifications methods supported in Progress Testing Framework</a> and insert actions against it. An example of this solution could be seen below:

![Different Logic][3]

## SOLUTION 2

If the test project is in a TFS source controlled environment when <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">run remotely/schedule</a> the test list (Step 2) there is an option - *"Get latest version of tests automatically from TFS"*. Once this option is enabled the entire project would be downloaded on the remote machine and compiled there exception free.

[1]: /img/troubleshooting-guide/scheduling-issues-tg/compilation-exceptions-when-execute-remotely/fig1.png
[2]: /img/troubleshooting-guide/scheduling-issues-tg/compilation-exceptions-when-execute-remotely/fig2.png
[3]: /img/troubleshooting-guide/scheduling-issues-tg/compilation-exceptions-when-execute-remotely/fig3.png
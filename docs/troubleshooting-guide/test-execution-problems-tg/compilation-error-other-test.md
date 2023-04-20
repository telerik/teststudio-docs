---
title: Compilation Error Concerning Other Test
page_title: Compilation Error in Test A When Executing Test B
description: "Test Studio test cannot be executed due to compilation errors related to other tests in the same project."
position: 1
---
# Compilation Error in Test A When Executing Test B

## PROBLEM

My project contains two or more tests that contain coded steps. I receive a compilation error for Test A when I try to execute Test B.

![Compilation error][1]

## SOLUTION

This is expected behavior. Anytime you execute a test that contains code (or calls a sub-test that includes code), all of the code must be compiled at once for the entire test project. If this was not done, then external/global functions you may have written in an external class file would not be included. If code in any test fails to compile, you will receive a compilation error.

One way to overcome this error is to fix whatever is causing it. If the test in question has no coded steps, it likely did at one time. If the View Class button is not disabled, that test has a code behind-file associated with it. If you no longer need that code, you can easily remove the code-behind file by clicking **Clear > Remove Script File** from the **Edit** ribbon.

Another approach is to use <a href="/features/test-maintenance/tests-in-development" target="_blank">the ___In Development__ flag</a> for the test, which produces the compilation error. That way it is excluded from the overall compilation process.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/compilation-error-other-test/fig1.png
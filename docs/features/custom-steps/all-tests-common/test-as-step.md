---
title: Test as Step
page_title: Test as Step
description: "How to reuse tests in Test Studio? Use a test as a step in another Test Studio test. Can I have a single function used in multiple scenarios - like logout, login and insert it in a larger test in Test Studio. "
position: 1
---

# Test as Step

The __Test as step__ feature allows you to run an existing test as a single step within another test. Using tests as step can help to reuse common automated steps across the project. This approach is also known as test modularization and includes breaking up the testing tasks into modules that do specific small functions on their own, but do not perform the complete end-to-end testing scenario.

This article describes how to add this type of step and demonstrates an example scenario.

- [Add test as step from Step Builder](#add-test-as-step)
- [Group existing steps into a new test as step](#group-recorded-steps-as-test-and-insert-it-as-step)
- [Example of using the tests as steps](#example-of-using-tests-as-step)

## Add Test as Step

Choose the __Test as Step__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Step Builder Test as step](/img/features/custom-steps/test-as-step/fig7.png)

On the next screen you can choose a test to add among all tests of the same type (web, WPF, desktop) in the project. Pick a test from the list and confirm the selection with pressing the __Select__ button.

![Choose a Test to add as step](/img/features/custom-steps/test-as-step/fig8.png)

> __Important!__
> <br>
> <br>
> Tests set <a href="/features/test-maintenance/tests-in-development" target="_blank">**'In development'**</a> and used as a step are always executed regardless their current state.

## Group Recorded Steps as Test and Insert It as Step

To ease the process of separating the test steps into smaller modules, Test Studio also gives the option to choose some already recorded steps and move them into a test. This test directly gets added as a step in the original test.

Let's use the following example - loading a URL in clear browser session forces the popup to accept the cookies. Record the steps to confirm the selection in the current test and insert these into a if..else condition. As these are repetitive actions to include in any other scenario, you can separate them into a new test - select the steps and choose the _Create Test as Step_ option from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">__Step Context Menu__</a>.

![Select steps to create test as step](/img/features/custom-steps/test-as-step/fig9.png)

The next screen lists the selected steps and lets you set a meaningful name for the new test. Confirm the new test by pressing the __Create__ button.

![Name and create the Test as step](/img/features/custom-steps/test-as-step/fig10.png)

It is directly inserted as a step in the original test. 

![New test added as step](/img/features/custom-steps/test-as-step/fig11.png)

## Example of Using Tests as Step

Below is a sample project automating Amazon.com:

![Project](/img/features/custom-steps/test-as-step/fig1.png)

The sample _Login_ test contains the following steps:

![Login Test](/img/features/custom-steps/test-as-step/fig2.png)

Open the _AddToCart_ test and insert the _Login_ test to its beginning using the __Test as Step__ option from the Step Builder. The Login test is added as a single step and all its steps gets executed before moving on to step 3 in this example.

![Test](/img/features/custom-steps/test-as-step/fig6.png)

> __Important!__
> <br>
> <br>
> Tests set <a href="/features/test-maintenance/tests-in-development" target="_blank">**'In development'**</a> and used as a step are always executed regardless their current state.

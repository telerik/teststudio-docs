---
title: Test as Step
page_title: Test as Step
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Test as Step

This feature allows you to run an existing test as a single step within another test. This can help to reuse common automated test steps in the project. This is also known as test modularization. The approach includes breaking up your testing tasks into modules that do specific small functions on their own, but do not perform the complete end-to-end testing scenario.

![Test as step 2015](/img/features/custom-steps/test-as-step/fig7.png)

Here is a sample project for Amazon.com:

![Project](/img/features/custom-steps/test-as-step/fig1.png)

Here is a sample Login test:


![Login Test](/img/features/custom-steps/test-as-step/fig2.png)

Once the test modules are in place, they could be added to high-level tests with the **Test as Step** function. Open *AddToCart* test and add the Login test to its beginning.


<table>
<tr>
<th> ![Test as Step](/img/features/custom-steps/test-as-step/fig3.png) <br><br> Step Builder is available in both Standalone Version and VS Plugin</th>
</tr>
<table>

Choose the Login test and click **Select**.


![Select Test](/img/features/custom-steps/test-as-step/fig5.png)

The Login test will be inserted into the AddToCart test as a single step. The steps of the Login test will be executed before moving on to step 3 in this example.

![Test](/img/features/custom-steps/test-as-step/fig6.png)

> Tests set with <a href="/features/test-maintenance/tests-in-development" target="_blank">**'In development'**</a> flag and used as test as step will be always executed regradless their current state. 
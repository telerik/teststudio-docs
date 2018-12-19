---
title: Using the Execution Log
page_title: Using the Execution Log
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/troubleshooting_guide/troubleshooting_tools/using_the_execution_log.aspx, /user-guide/troubleshooting_guide/troubleshooting_tools/using_the_execution_log
position: 1
---
# Using the Execution Log

The execution log or test log is a log available after test failure in the test view or as part of the <a href="/getting-started/test-results/step-failure-details" target="_blank">failure details</a>.
You can pull it out by clicking **View Log** button. 

![View Log][1]

or from failure details:

![Step failure details][2]

The execution log is a record of the steps executed in the test, whether they passed or failed, and if they failed, why. It records what actions a step takes and what elements it acts upon. It includes all steps in one sequence, regardless of whether they are part of the main parent test or a test as step.

![log][3]

It says what errors arose in the case of a failure, giving detailed information on where the error occurred, and whether the error caused the test to fail.

![log][4]

For these reasons, the execution log is an excellent resource for forming a clear story of what led to a failure.

**When to export the Execution Log?**

Anytime a test fails unexpectedly and without clear explanation, the execution log can help in determining the cause. This includes any of the following, when unexpected:

-          The test closes after waiting;

-          A step fails unexpectedly and the test continues;

-          The test fails without executing any steps;

**Exporting The Execution Log.**

In the Step Failure Details window, you can choose to export results to file, including the execution log.

**What to look for in the Execution Log**

The Execution Log lists four main types of information. Two of these, the action taken by the step and the element acted upon by the step, are included in the Test view. However, they can still be useful if the recipient of the execution log does not have access to the associated test (for example, the Test Studio support team). The other two categories of information are step execution properties (including whether to continue on failure and whether to break on execution) and error information. Each of these pieces of information is contained elsewhere in Test Studio, the Execution log provides a sequential summary of the entire test leading up to failure.

[1]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log/fig1.png
[2]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log/fig2.png
[3]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log/fig3.png
[4]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log/fig4.png

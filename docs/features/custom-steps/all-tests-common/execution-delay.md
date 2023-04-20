---
title: Execution Delay
page_title: Execution Delay
description: "How to make the execution of a test in Test Studio wait for some time. How can I slow down the test run in Test Studio. How to insert execution delay in Test Studio."
position: 4
---
# Execution Delay

The __Execution Delay__ step allows you to pause the test execution for the set amount of time in milliseconds.

This article describes how to add this type of step in the test.

Choose the __Execution Delay__ step from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Execution Delay Step](/img/features/custom-steps/execution-delay/fig1.png)

Change the amount of time to wait in the step's property _WaitTime_:

![Execution Delay properties](/img/features/custom-steps/execution-delay/fig2.png)

> __Tip__
> <br>
> <br>
> It is recommended to try synchronizing the test run with the help of a <a href="/features/recorder/highlighting-menu/quick-steps/quick-verification" target="_blank">verify</a> or <a href="/features/recorder/highlighting-menu/quick-steps/wait" target="_blank">wait</a> step which are related to elements from the page. The so called _'hard-coded'_ wait is to be used when there is no specific verification to handle need of wait.

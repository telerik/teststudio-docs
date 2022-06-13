---
title: Test as Step Results
page_title: Test as Step Results
description: "Learn how to use a Test Studio test as step results, also know as nesting test results."
position: 2
---
# Test as Step Results 

Test Studio allows you to combine commonly used steps in a test and reuse them by executing this <a href="/features/custom-steps/test-as-step" target="_blank">test as a step</a>. The test as step is presented as a single step in the parent test and its overall status after quick execution is marked passed or failed as for any other step.

You can find the details about the test as step execution and the outcome from each of its steps in the Quick execution log.

## Quick Execution Log for Test as Step

If the test as step is executed without errors and the rest of the test is successful, the overall test result will be marked as passed.

![Successful web test with test as step][1]

To review all executed actions, including these in the test as step, click the **View Log** button to open the quick execution log.

![Execution log for passed test as step][2]

## Failing Test As Step

If any of the steps in a test as step fails, the parent test is marked as failed, and the step, which calls the test, will be also marked as failed in the Test Steps pane.

![Failed web test with a test as step][3]

Clicking the **View Log** link displays both the overall test results and the results for the test as step.

![Execution log for failed test as step][4]

[1]: /img/automated-tests/test-results/test-as-step-results/fig1.png
[2]: /img/automated-tests/test-results/test-as-step-results/fig2.png
[3]: /img/automated-tests/test-results/test-as-step-results/fig3.png
[4]: /img/automated-tests/test-results/test-as-step-results/fig4.png
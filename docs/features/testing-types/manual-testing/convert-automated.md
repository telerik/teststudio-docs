---
title: Convert to Automated
page_title: Convert to Automated
description: "Convert manual Test Studio test to an automated one."

position: 4
---
# Convert Manual Test to an Automated

Once most or all of the steps of your manual test are automated, you can convert the test to an automated Web or WPF test.

1.&nbsp; Click the **Project** tab on the left bottom pane.

2.&nbsp; Highlight the manual test.

3.&nbsp; Click **All Test Properties** button.

4.&nbsp; Find the **IsManual** setting in the Properties pane.

5.&nbsp; When checked, the test is executed with the manual test runner:

- Mark manual steps as Pass, Fail, or NotRun.
- Fast Forward automated steps.

![IsManual][1]

6.&nbsp; When unchecked, the test is executed with automated test runner:

- If all steps are automated, no tester intervention is required and results are available upon test completion. 
- If the test still contains manual steps, the test will pause at each one and prompt the tester to execute the step, enter a comment, and Pass or Fail the step. Manual Steps in automated tests are outlined <a href="/features/custom-steps/manual-step" target="_blank">here</a>. 

![Unchecked][2]

[1]: /img/features/testing-types/manual-testing/convert-automated/navigate-to-props.png
[2]: /img/features/testing-types/manual-testing/convert-automated/ismanual-unchecked.png


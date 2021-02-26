---
title: Automatic Re-run of Failed Tests
page_title: Automatic Re-run of Failed Tests
description: "Test Studio Test List Execution. How to run a test list in Test Studio and Automatically rerun the failed test in a test list. "
position: 2
---
# How Automatic Re-run of Failed Tests Helps

Test Studio provides a rich set of <a href="/features/test-lists/test-list-settings" target="_blank">test list settings</a> to help for stable execution of the tei suites and easier debugging in case of failures.

Test lists are designed for unattended execution and as such, there are multiple circumstances, which can affect the test run temporary and report a false failure. For example, the application's under test responsiveness slows down for a short amount of time, and this causes a missing element failure. Upon the next execution of the same test, there is no further issue.

## Enable the Automatic Re-run Setting for a Test List

For similar occasions Test Studio allows you to __automatically re-run the failing tests in a test list__. Enabling this setting will be helpful in the cases of a temporary issue with connectivity or application accessibility and any failed tests will be executed automatically after the test list execution finishes. Hence, the amount of fake failures will be significantly reduced.

![Automatic Rerun Setting][3]

The <a href="/automated-tests/test-list-results/analyze-test-list-results#automatic-re-run-of-failed-tests-results" target="_blank">results of the second automatic execution</a> will be listed under the initial failed result of the same test. It will be marked with an exclamation mark.

> __Note__ 
><br>
><br>
> The tests need to be designed as autonomous tests - if these are dependent on the previous tests in the list, this setting will not be applicable.

[1]: /img/automated-tests/test-lists/test-list-runs-specifics/fig1.png
[2]: /img/automated-tests/test-lists/test-list-runs-specifics/fig2.png
[3]: /img/automated-tests/test-lists/test-list-runs-specifics/fig3.png
[4]: /img/automated-tests/test-lists/test-list-runs-specifics/fig4.png

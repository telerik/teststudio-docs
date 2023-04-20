---
title: If... Else Logical Step Fails
page_title: If... Else Logical Step Fails
description: "If... Else Logical Step Fails in a Test Studio test without determining any of the branches for execution"
position: 1
---
# If... Else Logical Step Fails

## PROBLEM

I added an **If...Else** logical step to my test. When the verification attached to the IF portion is true, that branch correctly executes. However, when that verification is false, the ELSE branch does not execute and the test fails.

## SOLUTION

The issue is likely with the verification attached to the IF portion. Let's say it verifies the element is visible. When the element does not exist and cannot be found, the verification cannot be performed, the ELSE portion is not executed, and the entire test fails.
 
The fix is to record a new verification on the element and attach it to the IF. This time, record a **Wait - element exists** step. This way, when the element does not exist, the ELSE portion will correctly execute and the test will not fail.

![Test Steps][1]

**See Also**

- <a href="/features/logical-steps/if-else" target="_blank">If else</a>

- <a href="/features/verifications/quick-verification" target="_blank">Quick Verification</a>

- <a href="/features/verifications/advanced-verification" target="_blank">Advanced Verification</a>

[1]: /img/troubleshooting-guide/test-execution-problems-tg/if-else-logical-step-fails/fig1.png

---
title: Does Not Exist in the Current Context
page_title: Test Studio Scheduling Error Does Not Exist in the Current Context
description: "Test Studio Scheduling. Executing a scheduled test list or remotely running a test list fails with error does not exist in the current context"
position: 1
---
# "Does Not Exist in the Current Context" Error in Test Studio Scheduled Test

## PROBLEM

When scheduling or executing a test list remotely via the <a href="/features/scheduling-test-runs/overview" target="_blank">Test Studio Scheduling setup</a>, a test in the test list fails with an error like this:

*error CS0103: The name 'Utility' does not exist in the current context*.

## SOLUTION

This behavior may occur when one or more tests in a scheduled test list rely on a static utility class in a test that is not included in the test list or used by any of the tests in that test list as a Test as Step. In this case, Test Studio will not send the excluded test to the Execution Server.

To resolve this behavior, use one of these two solutions:

- Add the test that contains the necessary utility class to the test list.

- Reference the test that contains the necessary utility class as a Test as Step in one of the tests in the test list.

> Using either of these solutions, you only need to run the test list with the utility test once each time you change the utility class. After this, the test list will be able to reference the utility class, even if you remove the utility test from the test list or remove the Test as Step.
<br>
<br>
**See Also**

- <a href="/advanced-topics/coded-samples/general/utility-class-in-standalone" target="_blank">Create a Utility Class in Test Studio Standalone</a>

- <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">Test Lists (Standalone)</a>

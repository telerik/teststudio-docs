---
title: Stop Test List On Failure
page_title: Stop Test List On Failure
description: "My tests in a test list are dependent and if one fails, the rest don't need to be executed because they will also fail. How to force stop a test list run if any of the tests fails?"
position: 1
---
# Stop Test List On Failure

## PROBLEM

You would like to stop execution on a test list if one of its tests encounters an error. Currently, when an error occurs, it marks that test as failed but continues to run the remaining tests in the list.

## SOLUTION

Enable the **StopTestListOnFailure** <a href="/features/test-maintenance/test-properties-standalone" target="_blank">Test Property</a> for the applicable test(s).


1.&nbsp; Go to the **Project** tab. 

2.&nbsp; **Highlight** the test.

3.&nbsp; Right click the test and select **Properties**.

4.&nbsp; Check the **StopTestListOnFailure** box.  

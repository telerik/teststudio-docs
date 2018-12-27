---
title: Using the DOM on Failure
page_title: Using the DOM on Failure | Test Studio Dev Documentation
description: The DOM on failure is a copy of the state of the DOM of the application at the time of failure.
position: 2
---
# Using the DOM on Failure

**What is the DOM on Failure?**

The DOM on failure is a copy of the state of the <a href="/features/recorder/dom-explorer" target="_blank">DOM</a> for the execution browser at the time a test fails. The DOM on Failure is available after test failure as part of the <a href="/features/failed-tests-debugging/step-failure-details" target="_blank">failure details</a>. 

![Page DOM][1]

> If similar issues occur with a test that passes, find the relevant element using the <a href="/features/recorder/dom-explorer" target="_blank">DOM Explorer</a>.

**When to use the DOM on Failure**

The DOM on Failure is most helpful in situations where a test does not properly locate and act on a particular element. This includes any of the following, when unexpected:

- ‘Element does not exist’ exceptions;

- ‘Element not found’ exceptions;

- ‘Timed out waiting for element’ exceptions;

- Test execution targets incorrect element.

**Exporting the DOM on Failure**

In the <a href="/features/failed-tests-debugging/step-failure-details" target="_blank">Step Failure Details</a> window, you can choose to export results to file, including the DOM on Failure.

**What to look for in the DOM on Failure**

The DOM on Failure provides a record of the elements that Test Studio Dev could see in the browser at the time the test failed. Compare with <a href="/features/elements-explorer/find-element" target="_blank">the find logic</a> of the element that Test Studio Dev expects to be in the browser during the failed step. This helps to identify which element should have been targeted, why the incorrect element may have been targeted, or what state the browser may have been in instead of the correct state.

[1]: images/using-the-dom-on-failure/fig1.png
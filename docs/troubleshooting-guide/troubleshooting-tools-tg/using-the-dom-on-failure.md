---
title: Using the DOM on Failure
page_title: Using the DOM on Failure
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Using the DOM on Failure


**What is the DOM on Failure?**

The DOM on failure is a copy of the state of the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM</a> for the execution browser at the time a test fails. The DOM on Failure is available after test failure as part of the <a href="/getting-started/test-results/step-failure-details" target="_blank">failure details</a>. 

![Page DOM][1]

> If similar issues occur with a test that passes, find the relevant element using the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM Explorer</a>.

**When to use the DOM on Failure**

The DOM on Failure is most helpful in situations where a test does not properly locate and act on a particular element. This includes any of the following, when unexpected:

- ‘Element does not exist’ exceptions;

- ‘Element not found’ exceptions;

- ‘Timed out waiting for element’ exceptions;

- Test execution targets incorrect element.

**Exporting the DOM on Failure**

In the <a href="/getting-started/test-results/step-failure-details" target="_blank">Step Failure Details</a> window, you can choose to export results to file, including the DOM on Failure.

**What to look for in the DOM on Failure**

The DOM on Failure provides a record of the elements that Test Studio could see in the browser at the time the test failed. Compare with <a href="/features/elements-explorer/find-element" target="_blank">the find logic</a> of the element that Test Studio expects to be in the browser during the failed step. This helps to identify which element should have been targeted, why the incorrect element may have been targeted, or what state the browser may have been in instead of the correct state.

[1]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-dom-on-failure/fig1.png
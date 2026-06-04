---
title: How to Use the Visual Debugger
page_title: Visual Debugger
description: "Test Studio Visual Debugger tools to explore why a test is failing. What is the Visual Debugger in Test Studio. How to use the Visual Debugger in Test Studio"
position: 9
---
# How to Use the Visual Debugger

The Visual Debugger is a useful tool, which allows you to debug a test while it is being executed. By default it is enabled for each quick test execution. It appears at the bottom right corner of the active display (right above the Windows system tray) and shows the progress of the executed steps.

The Visual Debugger tool provides a bunch of useful options to troubleshoot a failing step in test run-time and this article describes these in details.

## Enable/Disable the Visual Debugger Tool

The __default state of the Visual Debugger is enabled__ and it will appear for each quick test run triggered from the _Execute_ button. Since it appears on top of all other applications running on the desktop, including the execution browser, you may need to disable it in certain occasions. An example is a maximized browser and a test script, which interacts with controls on the page, which remain under the Visual Debugger tool. __Use the _Debugger_ toggle button__ in the __Test__ tools ribbon to enable or disable it.

![Visual Debugger toggle on or off](/img/automated-tests/troubleshooting/visual-debugger/fig1.png)

## Set Auto-Pause Rule for the Visual Debugger

The Visual Debugger can be stopped manually at any time of the test run using the _Pause_ button in the tool. For your convenience, Test Studio provides __few options to auto-pause the execution__ and allow you explore the momentum state of the application. The predefined rules, which can trigger the pause of the test run are:

- __On Element Find Errors Only__
- __On Verification Errors Only__
- __On Wait Errors Only__
- __On Any Errors__

![Visual Debugger auto-pause options](/img/automated-tests/troubleshooting/visual-debugger/fig2.png)

## Set Breakpoint

Along with these specific errors, you can choose any step from a test, prior which execution you want to pause the execution, and __set a breakpoint__ for it. The breakpoint for a step indicates pausing the test before the step is executed, if the Visual Debugger is enabled for the test run.

![Visual Debugger pause on breakpoint](/img/automated-tests/troubleshooting/visual-debugger/fig3.png)

## Manually Pause the Test

If you haven't set any of the auto-pause options, you can __manually pause the test run - hit the _Pause_ button__ directly in the Debugger tool.

![Visual Debugger manual pause](/img/automated-tests/troubleshooting/visual-debugger/fig4.png)

> __Note__
><br>
><br>
>The test run will __be paused once the listed current step execution finishes__. So, if this a failing step, which uses a timeout, before it reports the failure, the pause will be applied after the timeout passes.

## Make Use of the Visual Debugger Tool Options During Test Run

Once the test pauses, regardless if this is an auto-pause or a manual trigger of the _Pause_ button, the following Debug Options are available:

* __Show the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM Explorer</a> of the currently displayed page.__ This can help identify the correct find logic for a particular element, or whether a desired element is missing.

	![Visual Debugger Show DOM](/img/automated-tests/troubleshooting/visual-debugger/fig5.png)

* __Capture the currently failed state.__ Save a .zip file containing a snapshot of the DOM, browser image, and test log. You can use this complete record of the current page state to communicate it to a third party, such as a developer in your organization, or a Test Studio support engineer.

	![Visual Debugger capture state](/img/automated-tests/troubleshooting/visual-debugger/fig6.png)

* __Diagnose a failure directly.__ Only enabled on detected failures.

	![Visual Debugger diagnose failure, if applicable](/img/automated-tests/troubleshooting/visual-debugger/fig7.png)

	* Opens the <a href="/features/verifications/advanced-verification" target="_blank">Sentence Verification Builder</a> for failed Verifications.
	* Opens the <a href="/features/elements-explorer/find-element" target="_blank">Find Element</a> dialog for Unable to locate element failures. In combination with the DOM Explorer, this find logic can help diagnose steps that fail due to faulty find expressions.

* __View the current execution log of the test.__ Displays the execution log at the time of the current step. Since the execution log contains details on step failure, it can act as a starting point in your debugging. For example, if the failure log contains an 'Element does not exist' exception, you can check to see if the element is missing altogether or whether the step used bad find logic.

	![Visual Debugger View execution log](/img/automated-tests/troubleshooting/visual-debugger/fig8.png)

* __Send bugs directly to a bug tracker.__ Only enabled, if you have configured a bug tracker for the project. Opens the _Submit a Bug_ dialog, so you can easily record any bugs in the bug tracking app during debugging.

	![Visual Debugger Send Bug](/img/automated-tests/troubleshooting/visual-debugger/fig9.png)

## Resume the Test Execution

Once finished with debugging process for the current step, you have few options to continue the test execution.

* __Re-run current step__ using the _Rerun_ button.

	![Visual Debugger Re-run Current step](/img/automated-tests/troubleshooting/visual-debugger/fig10.png)

* __Execute one step at a time__ using the *Fast Forward* button.

	![Visual Debugger Execute one step at a time](/img/automated-tests/troubleshooting/visual-debugger/fig11.png)

* __Resume normal execution__ using the *Play* button.

	![Visual Debugger Resume normal execution](/img/automated-tests/troubleshooting/visual-debugger/fig12.png)

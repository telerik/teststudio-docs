---
title: Step Builder Panel
page_title: Add Steps from the Step Builder
description: "Custom steps in the Step Builder in Test Studio. Steps, which can be added only manually from the Step Builder. How to add a step for an already recorded element."
position: 0
---

# Use the Step Builder to Add Steps

The Advanced Recording Tools window can help build a wide range of automation and verification quickly and without having to resort to manual configuration. There are some common steps like adding a comment, or clearing the browser cache, which need to be added outside of the recorded actions. The __Step Builder__ pane in the project area provides a list of these additional steps and let's you maintain them in the tests.

Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">Test Studio project's layout</a> you use, the __Step Builder__ pane could be located on different place - usually on the right side of the project area, either <a href="/automated-tests/customize-project/custom-layout#hide-or-show-a-panel" target="_blank">pinned or hidden</a>.

![Step Builder Pane in Project][1]

## Add Step for a Recorded Element

The Step Builder can also be used to build steps against already recorded elements in the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the action or verification you need and click the **Add Step** button to insert the step in the test.

![Step Builder Actions and Verification][3]

> __Tip__
><br>
><br>
> You can check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

## Add a General Step from the Step Builder

The __General__ section in the __Step Builder__ is divided in three sub-sections - __Common__, __Conditions__ and __Dialogs__.

- The __Conditions__ section provides the option to add the built-in logical blocks - <a href="/features/logical-steps/if-else" target="_blank">if..else</a>, <a href="/features/logical-steps/loop" target="_blank">loop</a> and <a href="/features/logical-steps/while-loop" target="_blank">while..loop</a>.

- The __Dialogs__ section allows you to manually add steps for <a href="/features/dialogs-and-popups/dialogs" target="_blank">handling different dialogs</a>.

- The __Common__ section consists of different steps suggestions based on the type of test - web, desktop or WPF.

<table id="no-table">
	<tr>
		<td>![Common web test steps][5] <br><br>**Web Test**</td>
		<td>![Common WPF test steps][7] <br><br>**WPF Test**</td>
	</tr>
<table>

1. [Test as Step](/features/custom-steps/test-as-step) - run an existing test as a single step.
1. [API Test as Step](/features/execute-apitest/add-api-test-as-step) - run an existing API test as a single step.
1. [Navigate To](/features/custom-steps/navigate-to) - navigate to an URL step.
1. [Open PDF](/features/custom-steps/open-pdf) - insert step to open a locally stored PDF file .
1. [Coded Step](/features/custom-steps/script-step) - add a coded step and open the code editor.
1. [Execution Delay](/features/custom-steps/execution-delay) - pause the test for a specified amount of time.
1. [Maximize Browser](/features/custom-steps/maximize-browser) - maximize, minimize or restore the active browser (Change Window State for WPF).
1. [Clear Browser Cache](/features/custom-steps/clear-browser-cache) - clears all cookies, temp files or history from the active browser depending on the user's choice.
1. [Refresh Browser](/features/custom-steps/browser-refresh) - refresh the active browser.
1. [Capture Browser](/features/custom-steps/capture) - take a screenshot of only the browser or the entire desktop.
1. [Wait For URL](/features/custom-steps/wait-for-url) - pause the test until the specified URL is loaded into the browser address bar.
1. [Check for JS Errors](/features/custom-steps/check-js-errors) - verify if there are any JS errors on the page.
1. [Comment](/features/custom-steps/comment) - a comment as a step in the test
1. [Custom Annotation](/features/custom-steps/custom-annotation) - add a note to display when running "Quick Execution" with Annotation turned on.
1. [Inspection Point](/features/custom-steps/inspection-point) - pause the test and display the DOM Explorer.
1. [Manual Step](/features/custom-steps/manual-step) - display a dialog box to enter directions for a manual step.
1. [Change Window State](/features/custom-steps/change-window-state) - alter the state of the WPF application window.

[1]: /img/features/custom-steps/overview/use-the-step-builder-panel.png
[3]: /img/features/custom-steps/overview/AddSteps.png
[5]: /img/features/custom-steps/overview/web-gen-step.png
[7]: /img/features/custom-steps/overview/wpf-gen-step.png

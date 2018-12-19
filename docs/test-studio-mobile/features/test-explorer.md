---
title: Test Explorer
page_title: Test Explorer
description: Test explorer functioanlity
slug: ms-test-explorer
tags: test, explorer, mobile
publish: true
position: 2
previous_url: /test-studio-mobile/getting-started-mb/test-explorer
---
#Test Explorer

This section is dedicated to the Test Exlorer UI and functionality.

The Test Explorer pane shows open tests and the steps of the currently selected open test. The explorer features the following:

1. Active step column - a marker in this column shows the currently active test step. In recording mode this marker shows the position where the next recorded step will be added in the list. Only one step can be active step at a time.

	![Mobile Studio Active Step](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-active-step.png)

2. Enabled steps column - check box in front of each step indicates whether it is enabled. Disabled steps are not executed during playback no matter whether the step passes or fails. Multiple steps can be disabled at a time.

	![Mobile Studio Active Step](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-enabled-steps.png)

3. Continue on failure steps column - an icon in front of each step indicates whether test execution will continue even if the step fails. Normally, execution stops once a step fails. Multiple steps can be marked as `continue on failure` at a time.

	![Mobile Studio Continue Failure](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-continue-failure.png)

4. Expand/Collapse step column - based on the step type different parameters can be tweaked. Expand a step to see the options that can be changed. Only one step can be expanded at a time.

	![Mobile Studio Expand Step](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-expand-step.png)

5. Step description column - here the step index as well as a step display name is provided. The step display name is configurable through the properties pane.

	![Mobile Studio Step Display Name](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-step-displayname.png)

6. Step type column - indicates the step type - verification, action etc.

	![Mobile Studio Step Type](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-step-type.png)

7. Execution log and Error details - those buttons get active after a test is played back. The execution log provides details on a step by step basis. If a failure is detected, the log and the Error details are populated with descriptive error messages

	![Mobile Studio Error](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-error.png)

8. Context menu options showed upon right click on a step:

	* Delete, Cut, Copy and Paste operations.
	* Run test to specific step, run just selected steps or run from specific step. These options are available only when recording is currently active.

	![Mobile Studio Step ContextMenu](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-test-contextmenu.png)

9. Project explorer also features keyboard support that includes:

	* Selection navigation between steps with the **arrow keys** (up and down).
	* Deleting a step with the **Delete** key.
	* Cut (Ctrl+X), Copy (Ctrl+C) and Paste (Ctrl+V) steps.
	* Multi step selection using the Ctrl or Shift keys.

10. Steps support drag-drop to change their order in the list:

	![Mobile Studio Step Drag Drop](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-step-dragdrop.png)

11. Steps can be filtered by step type or step display name - use the filter field and search field at the top right corner of the pane. The search text is dynamic and once typing starts, steps will be filtered with every key stroke.

	![Mobile Studio Step Filtering](/img/test-studio-mobile/getting-started-mb/test-explorer/mobile-studio-step-filtering.png)


See Also
--------

* [Getting Started Native Apps]({% slug ms-getting-started-native%})
* [Getting Started Web Apps]({% slug ms-getting-started-web%})
* [Project Explorer]({% slug ms-project-explorer%})
* [Elements Explorer]({% slug ms-elements-explorer%})
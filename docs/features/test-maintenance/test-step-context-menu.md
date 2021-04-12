---
title: Test Step Context Menu
page_title: Test Step Context Menu
description: "Test Studio Test Step Context Menu with further actions that can be taken. Partial test run, Partial test execution, Run To Here, Convert verification step to wait, convert wait stei to extraction step, convert verification step to extraction step, create Test as step, Set Breakpoint, Continue On Failure, Edit a step in Code, Convert a step in code"
position: 1
---
# Test Step Context Menu

Each test step provides further actions that can be taken in the right mouse button context menu. Note that some of the items will show up or will be enabled only for certain test step types.

<table id="no-table">
<tr>
<td>![1][1]</td>
<td>![2][2]</td>
</tr>
<table>

---

&nbsp;=====================

- **Load Page** - launches the selected browser in record mode and loads the listed page; available for "Navigate to" steps only.
- **Open PDF** - launches the selected browser in record mode and loads the PDF file listed in the step; available for "Open PDF" steps only.
- **Rename** - alter the default step description.
- **Reset Name** - revert to the default step description.

---
&nbsp;=====================

The options in this section are only available for Verification steps!
- **Convert to Logical** - inserts the selected verification into a logical step.
  - **Convert to <a href="/features/logical-steps/if-else" target="_blank">if...else</a>** - insert the verification within a if...else block.
  - **Convert to <a href="/features/logical-steps/while-loop" target="_blank">while...loop</a>** - insert the verification within a while...loop block.
- **Edit** - loads the <a href="/features/verifications/advanced-verification" target="_blank">Sentence Verification Builder</a> for the selected verification.
- **Change Role** - toggles the selected verification type.
   - **Set as <a href="/features/verifications/advanced-verification" target="_blank">Verification</a>** - converts a Wait or Extract step to a Verification one.
   - **Set as <a href="/features/verifications/wait" target="_blank">Wait</a>** - converts a Verification or Extract step to a Wait one.
   - **Set as <a href="/features/verifications/extraction" target="_blank">Extraction</a>** - converts a Verification or Wait step to an Extract one.

---
&nbsp;=====================

- **Run** - partially executes the test to or from the selected step. Run bits of the test without having to run the entire test.
	- **To Here** - launches a new instance of the selected browser, execute the preceding (including the selected) test step(s), and finishes the run with recorder attached to the browser.
	- **From Here** - execute the subsequent steps in an existing browser instance (must have recording toolbar attached).
	- **Selected Steps** - execute the selected steps in an existing browser instance (must have recording toolbar attached).

---
&nbsp;=====================

- **Recording Marker** - move the marker to the step as selected:
	- **Move After This Step**
	- **Move Before This Step**
	- **Move After Last Step**

---
&nbsp;=====================

- **Create Test as Step** - the selected steps are moved into a new test, and that new test is inserted as a <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a>.
- **Open Test as Step** - active for a test as step; opens the test inserted as a step.
- **Open API Test as Step** - active for an <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">API test as step</a>; opens the API test inserted as a step.

---
&nbsp;=====================

- **Submit Bug** - loads the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and logs a bug in your previously configured bug tracking application.

---
&nbsp;=====================

- **Enabled** - choose whether the step will be run during execution.
- **Set Breakpoint** - choose whether the test pauses at that step and shows <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-visual-debugger" target="_blank">Debug Options</a>.
- **Continue On Failure** - whether the test stops or continues, if that step detects a failure.

---
&nbsp;=====================

- **Delete** - removes the selected steps from the test.
- **Cut** - cuts the selected steps from the test and allows you to paste these into another location in the same test, or in another test. Keyboard shortcut is Ctrl+X.
- **Copy** - copies the selected steps from the test and allows you to paste these into another location in the same test, or in another test. Keyboard shortcut is Ctrl+C.
- **Paste** - inserts the cut/copied steps in the desired test. Keyboard shortcut is Ctrl+V.

---
&nbsp;=====================

- **Edit in Code** - converts the recorded step to a new method in the coded file related to the test - <a href="/features/coded-steps/code-behind-file" target="_blank">the code-behind file</a>. Notice that the description and icon change to indicate the step is now a coded one. Once converted, it cannot be switched back to the initially recorded step.
- **View Code** - switches to the code-behind file and shows the test method for the selected coded step.

[1]: /img/features/test-maintenance/test-step-context-menu/fig1.png
[2]: /img/features/test-maintenance/test-step-context-menu/fig2.png
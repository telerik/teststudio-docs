---
title: Test Step Context Menu
page_title: Test Step Context Menu | Test Studio Dev Documentation
description: Test step context menu provides further options to edit and maintain steps in a Test Studio Dev test.
slug: features/step-context-menu
position: 5
---
# Test Step Context Menu

Each test step has a context menu with further actions that can be taken. Note that some context menu items will show up only for certain test step types.

<table id="no-table">
<tr>
<td>![Step Context Menu - Navigate][1]</td>
<td>![Step Context Menu][2]</td>
</tr>
<table>

---
&nbsp;=====================

- **Load Page** - launch the browser in record mode for "Navigate to" steps.
- **Rename** - alter the default step description.
- **Reset Name** - revert to the default step description.

---
&nbsp;=====================

The options in this section are only available for Verification steps!
- **Convert to Logical** - inserts the selected verification into a logical step.
  - **Convert to <a href="/features/logical-steps/if-else" target="_blank">if...else</a>** - insert the verification within a if...else block.
  - **Convert to <a href="/features/logical-steps/while-loop" target="_blank">while...loop</a>** - - insert the verification within a while...loop block.
- **Edit** - loads the <a href="/features/recorder/verifications/advanced-verification" target="_blank">Sentence Verification Builder</a> for the selected verification.
- **Change Role** - toggle the selected verification type.
   - **Set as <a href="/features/recorder/verifications/quick-verification" target="_blank">Verification</a>** - converts a Wait or Extract step to a Verification one.
   - **Set as <a href="/features/recorder/verifications/wait" target="_blank">Wait</a>** - converts a Verification or Extract step to a Wait one.
   - **Set as <a href="/features/recorder/verifications/extraction" target="_blank">Extraction</a>** - converts a Verification or Wait step to an Extract one.

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
- **Open API Test as Step** - this feature is supported in <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio Ultimate product</a> only.

---
&nbsp;=====================

- **Submit Bug** - this feature is supported in <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio Ultimate product</a> only.

---
&nbsp;=====================

- **Enabled** - choose whether the step will be run during execution.
- **Set Breakpoint** - choose whether the test pauses at that step and shows <a href="/features/failed-tests-debugging/using-the-visual-debugger" target="_blank">Debug Options</a>.
- **Continue On Failure** - whether the test stops or continues, if that step detects a failure.

---
&nbsp;=====================

- **Delete** - removes the selected steps from the test.
- **Cut** - cuts the selected steps from the test and allows you to paste these into another location in the same test, or in another test. Keyboard shortcut is Ctrl+X.
- **Copy** - copies the selected steps from the test and allows you to paste these into another location in the same test, or in another test. Keyboard shortcut is Ctrl+C.
- **Paste** - inserts the cut/copied steps in the desired test. Keyboard shortcut is Ctrl+V.

---
&nbsp;=====================

- **Edit in Code** - converts the recorded step to a new method in the coded file related to the test. Notice that the description and icon change to indicate the step is now a coded one. Once converted, it cannot be switched back to the initially recorded step.
- **View Code** - switches to the code-behind file and shows the test method for the selected coded step.

[1]: images/test-step-context-menu/fig1.png
[2]: images/test-step-context-menu/fig2.png
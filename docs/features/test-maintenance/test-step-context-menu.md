---
title: Test Step Context Menu
page_title: Test Step Context Menu
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/modifying-tests/test-step-context-menu.aspx, /user-guide/modifying-tests/test-step-context-menu
position: 1
---
# Test Step Context Menu

Each test step has a context menu with further actions that can be taken. Note that some context menu items will show up only for certain test step types.

<table id="no-table">
<tr>
<td>![1][1]</td>
<td>![2][2]</td>
</tr>
<table>

- Load Page - launch the browser in record mode for "Navigate to" steps.
- Edit in Code - creates a new test method in code. Notice that the description and icon change to indicate the step is coded. Once you convert, you cannot convert back.
- View Code - shows the code-behind for the selected coded step.

---
- Rename - alter the default step description.
- Reset Name - revert to the default step description.

---
- Convert to Logical - inserts the selected verification into a logical step.
  - Convert to <a href="/features/logical-steps/if-else" target="_blank">if...else</a>
  -  Convert to <a href="/features/logical-steps/while-loop" target="_blank">while...loop</a>
- Edit - loads the <a href="/features/verifications/advanced-verification" target="_blank">Sentence Verification Builder</a> for the selected verification.
- Change Role - toggle the selected verification type.
   - Set as <a href="/features/verifications/advanced-verification" target="_blank">Verification</a>
   -  Set as <a href="/features/verifications/wait" target="_blank">Wait</a>
   -  Set as <a href="/features/verifications/extraction" target="_blank">Extraction</a>

---

- Run - execute the test to or from the selected step. Run bits of the test without having to run the entire test.
	- To Here - launch a new instance of the selected browser, execute the preceding (and selected) test step(s), and enter recording mode.
	- From Here - execute the subsequent steps in an existing browser instance (must have recording toolbar attached).
	- Selected Steps - execute the selected steps in an existing browser instance (must have recording toolbar attached).

---

- Recording Marker - move the marker to the step:
	- Move After This Step
	- Move Before This Step
	- Move After Last Step

---

- Create Test as Step - the selected steps are moved into a new test, and that new test is inserted as a <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a>.

---

- Submit Bug - load the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and log a bug in your previously configured bug tracking application.

---

- Enabled - whether the step will run during execution.
- Set Breakpoint - whether the test will pause at that step and show Debug Options.
- Continue On Failure - whether the test will stop if that step detects a failure.

---
- Delete - remove the step from the test.
- Cut - keyboard shortcut is Ctrl+X
- Copy - keyboard shortcut is Ctrl+C
- Paste - keyboard shortcut is Ctrl+V


[1]: /img/features/test-maintenance/test-step-context-menu/fig1.png
[2]: /img/features/test-maintenance/test-step-context-menu/fig2.png
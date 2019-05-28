---
title: Quick Execution
page_title: Quick Execution.
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-execution/quick-execution.aspx, /user-guide/test-execution/quick-execution, /getting-started/quick-execution
position: 0
---
# Quick Execution #

> While a test is being executed **do not start another instance of the same browser** until the run is finished!

## Execute a Test ##

1.&nbsp; Once a test scenario is already recorded, click the **Execute** button in the Test ribbon.

<table id="no-table">
	<tr>
		<td>![Test Studio][1] <br><br>**Standalone version**</td>
	</tr>
	<tr>
		<td>![VS][2] <br><br>**VS plugin**</td>
	</tr>
<table>

1.1 &nbsp; Select the execution browser. This step will be skipped if you have already set a preferred browser from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Web ribbon</a>.

![Select browser][3]

2.&nbsp; The Test Studio Test Runner launches first in a command prompt window. This calls the set browser or application.

![Test Runner][4]

## Visual Debugger ##

By default in the lower right of your screen there is a ribbon which indicates the current step, includes play and pause ability, and shows additional Debug Options if you set a <a href="/features/test-maintenance/steps-pane" target="_blank">Breakpoint to any step</a>. This is the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-visual-debugger" target="_blank">visual debugger</a> and is a feature you could turn on or off.

![Visual Debugger Indicator][5]

## Debugger Options ##

Click **Debugging Options** icon in the Test ribbon or the Visual Studio toolbar to turn the debugger on/off and customize the Auto-Pause Options, if errors occur during the execution.

<table id="no-table">
	<tr>
		<td>![Test Studio][8] <br><br>**Standalone version**</td>
	</tr>
	<tr>
		<td>![VS][9] <br><br>**VS plugin**</td>
	</tr>
<table>

## Execute with Annotations ##

Click **Toggle Annotation** button to have the browser annotate each step with a brief message and by highlighting that step's element. This will also slow the test run down by inserting a delay between steps (in milliseconds) you set from either from the drop-down menu or by entering a custom value.

![Toggle Annotation][7]

## Execution Timeouts ##

Quick access to change the default timeouts for for **Wait on elements** and **Client ready** is also available through the test step pane.

![Timeouts][10]

## BaseURL ##

Set a **Base Url**, if you run tests against multiple environments. Please see our <a href="/knowledge-base/test-execution-kb/base-url" target="_blank">BaseURL KB article</a> for more information.

![BaseUrl][12]

## Compare Mode ##

When a **BaseURL** is set for the project, you can change the **Compare Mode** for future recorded elements. Detailed description of the different options can be found <a href="/features/project-settings/recording-options#elements-page-compare-mode" target="_blank">here</a>.

![Compare Mode][13]

## Preferred Browser ##

Under **Preferred browser** you can set your preferred browser for recording and execution and quick access the calibrate browsers view.

![Preferred browser][14]

## Execution Results ##

Afterwards, when the test execution is complete, test results are automatically generated and can be reviewed. Click **View Log** for test results details.

![View log][6]

[1]: /img/getting-started/test-execution/quick-execution/fig1.png
[2]: /img/getting-started/test-execution/quick-execution/fig2.png
[3]: /img/getting-started/test-execution/quick-execution/fig3.png
[4]: /img/getting-started/test-execution/quick-execution/fig4.png
[5]: /img/getting-started/test-execution/quick-execution/fig5.png
[6]: /img/getting-started/test-execution/quick-execution/fig6.png
[7]: /img/getting-started/test-execution/quick-execution/fig7.png
[8]: /img/getting-started/test-execution/quick-execution/fig8.png
[9]: /img/getting-started/test-execution/quick-execution/fig9.png
[10]: /img/getting-started/test-execution/quick-execution/fig10.png
[11]: /img/getting-started/test-execution/quick-execution/fig11.png
[12]: /img/getting-started/test-execution/quick-execution/fig12.png
[13]: /img/getting-started/test-execution/quick-execution/fig13.png
[14]: /img/getting-started/test-execution/quick-execution/fig14.png
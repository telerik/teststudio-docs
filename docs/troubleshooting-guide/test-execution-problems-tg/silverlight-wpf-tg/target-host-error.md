---
title: Target Host Error
page_title: Unable to Find the Target Host
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Unable to Find the Target Host

## PROBLEM

I'm trying to run a Silverlight test from Quick Execution, as part of a test list, or through the Telerik Testing Framework. The test fails with the Unable to find the target host error at the initial stages.

## SOLUTION

This is likely related to the test settings. This errors frequently shows up when you add a coded step that performs actions against Silverlight elements in your test. There are a few things you need to check:

- If you're running the test from Quick Execution in the Standalone version, go to the Project tab and check whether the test's *SilverlightEnabled* <a href="/features/test-maintenance/test-properties-standalone" target="_blank">Test Property</a> is set to True.

- If you're running the test as part of a test list (applicable for the Standalone version and VS plugin), check whether the SilverlightEnabled property is set to True on the Web tab of <a href="/getting-started/test-execution/test-list-settings" target="_blank">Test List Settings</a>.

- Increase the Silverlight Connect Timeout in Project Settings > <a href="/features/project-settings/recording-options" target="_blank">Recording Options</a>.

- If running the test as part of a test list, increase the Silverlight Connect Timeout on the Web tab of <a href="/getting-started/test-execution/test-list-settings" target="_blank">Test List Settings</a>..

- If you're using the Telerik Testing Framework, ensure your test includes the code below as the first line of your test. This is seen in <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/silverlight-ui-automation" target="_blank">this example</a>.

	

	Settings.Current.Web.EnableSilverlight = true;

> These solutions apply only for execution-related problems with Silverlight (i.e. you were able to record a test successfully). If you're unable to connect the recorder to your Silverlight application to record a test, see <a href="/troubleshooting-guide/recording-problems-tg/silverlight-unable-connect" target="_blank">this article</a>.

<br>
> If you receive this error for a non-Silverlight test that contains frames, see the bottom of <a href="/getting-started/test-recording/Frames" target="_blank">this page</a>.
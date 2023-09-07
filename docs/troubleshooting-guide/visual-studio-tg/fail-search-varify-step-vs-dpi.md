---
title: Fail Search or Verify Step in Visual Studio
page_title: Fail Search or Verify Step in Visual Studio
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Fail Search or Verify Step in Visual Studio

## PROBLEM

Еlement searches or verification related tasks that pass in “Quick Execution” or inside Test Studio, fail in Visual Studio Test Explorer plug-in.

*Reason: Visual Studio’s runners – testhost.exe have different built-in DPI scaling option.*

## SOLUTION

1.&nbsp; Go to “C:\Program Files\Microsoft Visual Studio\2022\[VS Edition]\Common7\IDE\Extensions\TestPlatform”

2.&nbsp; 2.	Open file properties for the appropriate runner. This one is tricky since the underlying runner can be changed from within Visual Studio:

![VsTestDropDown][1]

The default should be: “testhost.exe”

3.&nbsp; In file properties go to “Compatibility” tab.

4.&nbsp; Click “Change High DPI settings”.

5.&nbsp; Force the process to use the system specified DPI:

![TestHostDialog][2]

[1]: /img/troubleshooting-guide/visual-studio-tg/fail-search-verify-step-dpi/vs-test-dropdown.png
[2]: /img/troubleshooting-guide/visual-studio-tg/fail-search-verify-step-dpi/testhost-dialog.png
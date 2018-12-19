---
title: Tests Not Executed in Chrome or Firefox
page_title: Tests Not Executed in Chrome or Firefox
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Tests Not Executed in Chrome or Firefox

## Problem

Test Studio <a href="/getting-started/configure-your-browser/Chrome" target="_blank">Chrome</a> or <a href="/getting-started/configure-your-browser/Firefox" target="_blank">Firefox</a> browser latest extensions have been installed and browsers properly <a href="/features/project-settings/browsers" target="_blank">calibrated</a>. But it's still not possible to execute/record a test using those browsers and the following exception appears in the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log" target="_blank">execution log</a>.

```
[Date, Time] - Error attempting to exit runner. Error: System.IO.IOException: Pipe is broken.
   at System.IO.Pipes.PipeStream.WinIOError(Int32 errorCode)
   at System.IO.Pipes.PipeStream.WriteCore(Byte[] buffer, Int32 offset, Int32 count)
   at System.IO.Pipes.PipeStream.Write(Byte[] buffer, Int32 offset, Int32 count)
   at ArtOfTest.WebAii.Messaging.Process.PipeCommunication.WriteCommandToPipe(PipeCommand command, PipeStream pipe, Boolean waitForDrain)
   at ArtOfTest.WebAii.Design.Execution.RunnerController.Exit()
```

## Solution

The exception indicates that the communication between the product and the browser extension has been broken and no further test recording or execution is possible. Such problem is most probably caused by an active firewall or anti-virus software on the testing machine. Try to stop or deactivate that software to resolve the problem.

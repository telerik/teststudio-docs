---
title: Package Load Failure
page_title: Package Load Failure
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Package Load Failure

## PROBLEM

You receive a "Package Load Failure" error message while running Visual Studio after installing Test Studio. 

![Load Failure][1]

## SOLUTION

The error may appear due to missing "Unit Testing Tools" package in Visual Studio. There is an option to uncheck those tools when installing Visual Studio 2008. Installing the tools back will resolve the problem. 

To troubleshoot the error further, follow the steps from the MSDN blog post <a href="http://blogs.msdn.com/dr._ex/archive/2006/12/14/debugging-package-load-failures.aspx" target="_blank">here</a>.

1.&nbsp; Open a command prompt and then change to the IDE subdirectory. Normally, for VS2012, the default is:

  **C:\Program Files\Microsoft Visual Studio 11.0\Common7\IDE**

2.&nbsp; Enter: *devenv /ResetSkipPkgs* at the command prompt. The purpose is to reset any Skip Package Load flags that were turned on during previous sessions. See if you still get the Package Load Failure dialog.

3.&nbsp; If you do, then we're going to ask for you to create a log of VS2008 loading. To do that, exit VS2012, and at the command prompt enter:

  *devenv /log*

4.&nbsp; Let VS load and get the error, close the error dialog, and close VS. A log should have been created, but you may have to do a little hunting for it because it's created in your AppData folder. Typically this is:

  **C:\Users\<username>\AppData\Roaming\Microsoft\VisualStudio\11.0**

5.&nbsp; The file is called **ActivityLog.xml**. Please send us that file to study. Open a support ticket to attach files.

[1]: /img/troubleshooting-guide/cannot-launch-test-studio-tg/package-load-failure/fig1.png
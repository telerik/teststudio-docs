---
title: Error Adding Files
page_title: Error Adding Files
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: false
---
# Error Adding Files

## PROBLEM

Test Studio attempts to check out a test from TFS every time Test Studio opens, even when that test has not been recently checked in to TFS. 

An error like this appears in the application log:

<pre>
[02/04 14:33:22,Telerik.TestStudio.exe(2920:1),TeamFoundationServer] TFSServer._vcs_NonFatalError() : Non-fatal error handling TFS request: Failure instance 52192065
  RequestType: None
  Code: ItemExistsException
  Severity: Error
  Warnings: [0]
  ComputerName:
  IdentityName:
  LocalItem:
  Message: The item $/TestName.tstest already exists.

  [ . . .]

 [02/04 14:33:22,Telerik.TestStudio.exe(2920:1),TeamFoundationServer] TFSServer.AddFiles() : Error adding files
</pre>

## SOLUTION

This behavior may occur if you attempt to open a project on your local hard drive that was connected to a different TFS workspace. 


Instead of copying the project from another machine, try <a href="/features/source-control/open-tfs-project" target="_blank">opening it from TFS</a>. This way, Test Studio can properly setup the TFS workspace on your local machine.


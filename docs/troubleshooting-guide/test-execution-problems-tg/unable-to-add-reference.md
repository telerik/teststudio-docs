---
title: Unable to Add Reference
page_title: Unable to Add Reference
description: "Learn how to resolve errors when adding assembly references in Test Studio projects. This article explains common causes, such as referencing DLLs in hidden folders, and provides steps to fix reference and compilation issues."
position: 1
---
# Unable to Add Reference

## PROBLEM

When running a test project, the test fails with the following error in the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log" target="_blank">application log</a>:

**09/03 10:53:15,Telerik.TestStudio.RemoteExecutor.exe(15300:14),ProjectModel] Project.Compile() : Unable to add reference Project2012SP2\Profiler Configurations\ClassLibrary5.dll.<br>
Exception: System.IO.FileLoadException: The given assembly name or codebase was invalid. (Exception from HRESULT: 0x80131047)**

Later in the application log, a second error appears:

**[09/03 10:53:15,Telerik.TestStudio.RemoteExecutor.exe(15300:14),Execution] TestPlatform.OnRunnerError() : Error during remote runner execution: Compile failed: c:\Users\yee\AppData\Local\Temp\1\Projects\ce1cb993-aea7-46e9-9aa1-5d0493ddf4fc\Project2012SP2\Assembly.tstest.cs(18,7) : error CS0246: The type or namespace name 'ClassLibrary5' could not be found (are you missing a using directive or an assembly reference?)**

## SOLUTION

This behavior may occur when you try to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">add an assembly reference</a> to a DLL located in a hidden project folder.  These are: bin, Properties, obj, Backup, TestResults, Results, TestLists, Profiler, and Configurations.


To resolve this issue:

1.&nbsp; Move the external DLL to a different location within the project that is not in one of these hidden folders. 

2.&nbsp; Remove and re-add the reference to the external DLL in the Project Settings screen.

---
title: Built by Newer Runtime
page_title: This Assembly Is Built by a Runtime Newer than the Currently Loaded Runtime
description: "Learn how to resolve the 'assembly built by a newer runtime' error in Test Studio. This article explains the cause, provides troubleshooting steps, and details the correct way to run ArtOfTest.Runner.exe for successful test execution."
position: 1
---
# This Assembly Is Built by a Runtime Newer than the Currently Loaded Runtime

## PROBLEM

When using ArtOfTest.Runner.exe on the Execution Server, you receive one of these errors about a difference in versions:

*System.BadImageFormatException: Could not load file or assembly '___' or one of its dependencies. This assembly is built by a runtime newer than the currently loaded runtime and cannot be loaded.<br>
System.BadImageFormatException: This assembly is built by a runtime newer than the currently loaded runtime and cannot be loaded. (Exception from HRESULT: 0x8013101B)*

## SOLUTION

It is not permissible to make a copy of ArtOfTest.Runner.exe and execute it from a different location. There is a dependency that requires it to be run from its original location. This is true even if a system environment variable points to that location. By default the location is:

- **C:\Program Files (x86)\Progress\Test Studio\Bin**

 

For more information please see our user's guide article on <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a>. 


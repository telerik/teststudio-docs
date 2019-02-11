---
title: Built by Newer Runtime
page_title: This Assembly Is Built by a Runtime Newer than the Currently Loaded Runtime
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/troubleshooting_guide/test-execution-problems/assembly-built-by-newer-runtime.aspx, /user-guide/troubleshooting_guide/test-execution-problems/assembly-built-by-newer-runtime
position: 1
---
# This Assembly Is Built by a Runtime Newer than the Currently Loaded Runtime

## PROBLEM

When using ArtOfTest.Runner.exe on the Execution Server, you receive one of these errors about a difference in versions:

*System.BadImageFormatException: Could not load file or assembly '___' or one of its dependencies. This assembly is built by a runtime newer than the currently loaded runtime and cannot be loaded.<br>
System.BadImageFormatException: This assembly is built by a runtime newer than the currently loaded runtime and cannot be loaded. (Exception from HRESULT: 0x8013101B)*

## SOLUTION

It is not permissible to make a copy of ArtOfTest.Runner.exe and execute it from a different location. There is a dependency that requires it to be run from its original location. This is true even if a system environment variable points to that location. By default the location is:

- **C:\Program Files (x86)\Telerik\Test Studio 20XX.X\Bin**

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

For more information please see our user's guide article on <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a>. 


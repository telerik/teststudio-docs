---
title: System Requirements
page_title: System Requirements | Test Studio Dev Documentation
description: The minimum system requirements to automate tests with Test Studio Dev. 
slug: prerequisites/system-requirements
tags: requirements, system, minimum
position: 0
---
# System Requirements

__Test Studio Dev__ is a Visual Studio extension and inherits all the system requirements that  Visual Studio versions have. You can check the system requirements for supported versions <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2017-system-requirements-vs" target="_blank">Visual Studio 2017</a>, <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2015-sysrequirements-vs" target="_blank">Visual Studio 2015</a>, <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2013-sysrequirements-vs" target="_blank">Visual Studio 2013</a> or <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2013-sysrequirements-vs#vs2012" target="_blank">Visual Studio 2012</a>.

## User Account Control (UAC)

* If you are using Internet Explorer for test recording, the UAC needs to be set to 'Never Notify' in corresponding Settings page.

## Recommended Browsers

* Internet Explorer 11
* Chrome latest version
* FireFox latest version
* Edge latest version
* Safari latest version (5.1.7)

## Visual Studio requirements

* The extension can be used with Professional or higher version of Visual Studio 2012, 2013, 2015 and 2017. 
* You must run Visual Studio as Administrator
* Visual Studio projects should target .Net 4.5 or higher.

## Data Binding

* Microsoft Office installation or <a href="https://www.microsoft.com/en-us/download/details.aspx?id=23734" target="_blank">Microsoft Data Connectivity Components</a> (x86 redistributable).

## Framework

* <a href="https://www.microsoft.com/en-us/download/details.aspx?id=42642" target="_blank">.NET 4.5</a> or higher

## Source Control

* __Test Studio Dev__ uses the built-in TFS integration in Visual Studio  

## Build Server / Continuous Integration

If executing via <a href="/features/test-runners/mstest" target="_blank">MSTest</a> you will need

* Visual Studio (see above requirements) with VS plugin, __or__

* MSTest.exe installed on agent and controller

* Test Studio Dev Runtime or above installed on agent

If executing via <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a>

* <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Run-Time edition</a> is needed

## Beta Software

* Operating systems and web browsers in the beta stage are not supported.
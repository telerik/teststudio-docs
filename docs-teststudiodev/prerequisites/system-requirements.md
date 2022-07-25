---
title: System Requirements
page_title: System Requirements | Test Studio Dev Documentation
description: The minimum system requirements to automate tests with Test Studio Dev. 
slug: prerequisites/system-requirements
tags: requirements, system, minimum
position: 0
---
# System Requirements

__Test Studio Dev__ is an extension for Visual Studio tool and as such it inherits the requirements for the Visual Studio product family. Check the specific system requirements for each supported version of Visual Studio from the links below.

- <a href="https://docs.microsoft.com/en-us/visualstudio/releases/2022/system-requirements" target="_blank">Visual Studio 2022</a>
- <a href="https://docs.microsoft.com/en-us/visualstudio/releases/2019/system-requirements" target="_blank">Visual Studio 2019</a>
- <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2017-system-requirements-vs" target="_blank">Visual Studio 2017</a>
- <a href="https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2015-sysrequirements-vs" target="_blank">Visual Studio 2015</a>

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## User Account Control (UAC)

* If you are using Internet Explorer for test recording, the UAC needs to be set to 'Never Notify' in corresponding Settings page.

## Recommended Browsers

* Internet Explorer 11
* Chrome latest version
* Firefox latest version
* Edge Chromium latest version

## Visual Studio requirements

* The **Test Studio Dev** extension can be installed on Visual Studio 2015, 2017, 2019 and 2022 **Professional or Enterprise** edition.
* You must run Visual Studio as Administrator
* Visual Studio projects should target .Net 4.5.2 or higher
* Visual Studio 2017 requires additional <a href="/advanced-topics/installation/vs-2017-compatibility" target="_blank">Individual components</a> on top of its default installation

## Data Binding

* Microsoft Office installation or <a href="https://www.microsoft.com/en-us/download/details.aspx?id=23734" target="_blank">Microsoft Data Connectivity Components (x86 redistributable)</a>.

## .NET Framework

* <a href="https://www.microsoft.com/en-us/download/details.aspx?id=42642" target="_blank">.Net 4.5.2 - .Net 4.8</a> 
## Source Control

* __Test Studio Dev__ uses the built-in TFS integration in Visual Studio  

## Build Server / Continuous Integration

* The minimum installation on agent machine for running Test Studio Dev tests is the <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Run-Time edition</a>. It enables you to execute tests with the CLI runner called <a href="/features/cli-runner" target="_blank">ArtOfTest.Runner</a>

## Beta Software

* Operating systems and web browsers in the beta stage are not supported.

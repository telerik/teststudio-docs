---
title: System Requirements
page_title: System Requirements - Test Studio Dev Documentation
description: The minimum system requirements to automate tests with Test Studio Dev. 
slug: prerequisites/system-requirements
tags: requirements, system, minimum
position: 0
---
# System Requirements

__Test Studio Dev__ is an extension for Visual Studio tool and as such it inherits the requirements for the Visual Studio product family. Check the specific system requirements for each supported version of Visual Studio from the links below.

- <a href="https://docs.microsoft.com/en-us/visualstudio/releases/2022/system-requirements" target="_blank">Visual Studio 2022</a>
- <a href="https://docs.microsoft.com/en-us/visualstudio/releases/2019/system-requirements" target="_blank">Visual Studio 2019</a>



{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}


## Recommended Browsers

* Chrome latest version
* Edge Chromium latest version
* Firefox latest version

## Supported WPF and Desktop Applications 

* __WPF__ for .NET Framework 4.5+, .NET Core 3.1, .NET 5, .NET 6, .NET 7, .NET 8, .NET 9
* All Windows __desktop applications__ supporting the Microsoft UI Automation framework, including applications containing custom controls that provide the required automation peers.

## Visual Studio Requirements

* **Test Studio Dev** is compatible with Visual Studio 2019 and Visual Studio 2022.

    * Visual Studio projects target a version between .NET Framework 4.7.2 to .NET Framework 4.8.
    * Visual Studio 2022 requires minimum <a href="/advanced-topics/installation/vs-2022-compatibility" target="_blank">workload components selection</a>.

> **Important** 
><br>
> Test Studio Dev Edition ends support for Visual Studio 2019 at the beginning of 2026. 

## .NET Framework

* <a href="https://www.microsoft.com/en-us/download/details.aspx?id=42642" target="_blank">.Net 4.7.2 - .Net 4.8</a> 

## Source Control

* __Test Studio Dev__ uses the built-in TFS integration in Visual Studio  

## Build Server / Continuous Integration

* The minimum installation on agent machine for running Test Studio Dev tests is the <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Run-Time edition</a>. It enables you to execute tests with the CLI runner called <a href="/features/cli-runner" target="_blank">ArtOfTest.Runner</a>

## Beta Software

* Operating systems and web browsers in the beta stage are not supported.

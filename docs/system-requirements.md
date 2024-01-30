---
title: System Requirements
page_title: System Requirements
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/installation/system-requirements.aspx, /user-guide/installation/system-requirements, /getting-started/installation/system-requirements
position: 1
---
# System Requirements

<style>
.Pricing-head td {text-align: center;border-left: 1px solid #fff; vertical-align: top;}

.Pricing-head td:first-child {border-left: none;}

.Pricing-features--grid td.Pricing-head {padding: 20px 0!important;} 


.Pricing-head{border-collapse: separate;background-color: #2a2d33;}

.Pricing-head h4 {color: #589FBA; font-size: 16px; margin-bottom: 5px;min-height: 1em;font-weight: 700;}

table{width: 100%; border-spacing: 0; border-collapse: collapse; background-color: transparent; display: table;margin: 0;}

.Table--style1.Table--comparison td:first-child, .Table--style1.Table--comparison th:first-child {padding-left: 5px; text-align: left;}

.Table-RowDivision td, .Table-RowDivision th{background: #f3f5f7;}

.Table--style1 td, .Table--style1 th{padding: 8px 0 7px; border-left: 0;border-right: 0;vertical-align: middle;}

.Table--style1 thead td, .Table--style1 thead th{border: 0;padding-bottom: 12px;}

</style>

<table class="Tbl k-table">
    <colgroup>
        <col width="13%" />
        <col width="30%" />
        <col width="28%" />
        <col width="28%" />
    </colgroup>
    <tbody>
        <tr>
            <td style="background-color:#5f6977;">&nbsp;</td>
            <td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;">Disk Space</td>
            <td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;">CPU</td>
            <td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;">RAM</td>
        </tr>
        <tr>
            <td>Minimum</td>
            <td style="text-align:center;" align="center">500MB</td>
            <td style="text-align:center;">1.8GHz</td>
            <td style="text-align:center;">2GB</td>
        </tr>
        <tr>
            <td>Recommended</td>
            <td style="text-align:center;">2GB+</td>
            <td style="text-align:center;">2.2GHz+</td>
            <td style="text-align:center;">4GB+</td>
        </tr>
    </tbody>

</table>
<table class="Tbl k-table">
    <colgroup>
        <col width="15%" />
        <col width="80%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="6" style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;text-align:left;">Display<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Minimum</td>
            <td colspan="6" style="text-align:center;">1280 x 720</td>
        </tr>
        <tr>
            <td>Recommended</td>
            <td colspan="6" style="text-align:center;">1920 x 1080</td>
        </tr>
        <tr>
            <td>Display Scale</td>
            <td colspan="6" style="text-align:center;">100%</td>
        </tr>
    </tbody>
</table>
<table class="Tbl k-table">
    <colgroup>
        <col width="100%" />
    </colgroup>
    <thead>
        <tr>
			<td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;text-align:left;">Supported Operating Systems<td>
		</tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="4">Windows 11, Windows 10, &nbsp; <br>Windows Server 2022, Windows Server 2019, Windows Server 2016</td>
        </tr>
    </tbody>
</table>
<table class="Tbl k-table">
    <colgroup>
        <col width="100%" />
    </colgroup>
    <thead>
        <tr>
			<td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;text-align:left;">Supported Browsers<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="4">Internet Explorer 11, Latest Edge Chromium, Latest Chrome, Latest Firefox</td>
        </tr>
    </tbody>
</table>
<table class="Tbl k-table">
    <colgroup>
        <col width="100%" />
        </colgroup>
    <thead>
        <tr>
			<td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;text-align:left;">WPF Support<td>
		</tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="4">WPF for .NET Framework 4.5+, .NET Core 3.1, .NET 5, .NET 6, .NET 7</td>
        </tr>
    </tbody>
</table>
<table class="Tbl k-table">
    <colgroup>
        <col width="100%" />
        </colgroup>
    <thead>
        <tr>
			<td style="color:white;text-align:center;background-color:#5f6977;font-weight:bold;text-align:left;">Windows Desktop Applications Support<td>
		</tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="4">All Windows desktop applications supporting the Microsoft UI Automation framework, including applications containing custom controls that provide the required automation peers.</td>
        </tr>
    </tbody>
</table>

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Admin Rights

Admin permissions are required for:

- Test Studio installation process - initial install, modification of existing installation, uninstall.
- Test Studio Services installation and configuration - to enable the Scheduling setup for remote test execution.

## User Account Control (UAC)

* User Account Control Settings set to __'Never Notify'__.

## Visual Studio Plug-in Support

* IDE (Visual Studio plug-in only): Visual Studio __Professional or Enterprise 2017, 2019__ and __2022__.

	* You must run Visual Studio as Administrator.
	* Visual Studio projects target a version between .NET Framework 4.7.2 to 4.8.1.
    * Visual Studio 2022 requires <a href="/prerequisites/installation/installation-consideration#visual-studio-2022-installation-specifics" target="_blank">minimum selection of components</a> to add in its installation.
	* Visual Studio 2017 requires additional <a href="/prerequisites/installation/installation-consideration#modify-the-visual-studio-2017-installation" target="_blank">individual components</a> on top of its default installation.

> **Note** 
><br>
> Test Studio ends support for Visual Studio 2017 with release 2024 Q1 expected in the second half of February 2024.


## .NET Framework

* <a href="https://dotnet.microsoft.com/en-us/download/dotnet-framework/net472" target="_blank">__.NET Framework 4.7.2__</a>

## Required Database for Scheduling Configuration

* MongoDB 4.0 - 6.3

> **Note** 
><br>
> MongoDB requires at least __2 GB additional disk space__ on the machine where the Storage service is installed.

## Data Binding

* If using Excel or CSV for data driven testing:

	*	Microsoft Office installation or the **32-bit version** of <a href="https://www.microsoft.com/en-us/download/details.aspx?id=13255" target="_blank">Microsoft Access Database Engine 2010</a>.

## Source Control

* Git based repositories.

* Azure DevOps TFVC and Git based repositories.

## Build Server / Continuous Integration

* Integrating <a href="/features/test-runners/artoftest-runner" target="_blank">CLI Runner</a> test execution __requires minimum installation of the Test Studio <a href="https://www.telerik.com/teststudio/test-studio-runtime" target="_blank">Run-Time Edition</a>__.

## Beta Software

* Operating systems and web browsers in beta stage are __not supported__.
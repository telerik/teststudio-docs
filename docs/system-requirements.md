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

<div class="sfContentBlock"><table class="Pricing-head Pricing-features--grid Pricing-features--grid-4" style="margin-left: 12%; width: 88%;"> <tbody> <tr><td class="Pricing-head"> <h4>Windows 7, <br>
            Windows Server 2008</h4> </td> <td class="Pricing-head"> <h4>Windows 8, <br>
            Windows Server 2012</h4> </td> <td class="Pricing-head"> <h4>Windows 10, <br>
            Windows Server 2016</h4> </td> </tr> </tbody> </table>
</div>
<div class="sfContentBlock"><table class="Table Table--style1 Table--comparison"> <colgroup> <col width="18%" /> <col width="20%" /> <col width="28%" /> <col width="20%" /> <col width="10%" /></colgroup><thead> <tr class="Table-RowDivision"> <td colspan="5"><strong>Disk Space</strong></td> </tr> </thead> <tbody> <tr> <td>Minimum</td><td>500MB</td> <td>500MB</td><td>500MB</td> </tr> <tr> <td>Recommended</td> <td>2GB+</td> <td>2GB+</td><td>2GB+</td></tr> </tbody> </table> <table class="Table Table--style1 Table--comparison"> <colgroup> <col width="18%" /> <col width="20%" /> <col width="28%" /> <col width="20%" /> <col width="10%" /> <thead> <tr class="Table-RowDivision"> <td colspan="5"><strong>Processor</strong></td> </tr> </thead> <tbody> <tr> <td>Minimum</td> <td>1.8GHz</td> <td>1.8GHz</td> <td>1.8GHz</td> </tr> <tr> <td>Recommended</td> <td>2.2GHz+</td> <td>2.2GHz+</td> <td>2.2GHz+</td> </tr> </tbody> </table> <table class="Table Table--style1 Table--comparison"> <colgroup> <col width="18%" /> <col width="20%" /> <col width="28%" /> <col width="20%" /> <col width="10%" /><thead> <tr class="Table-RowDivision"> <td colspan="5"><strong>Memory</strong></td> </tr> </thead> <tbody> <tr> <td>Minimum</td> <td>1GB</td> <td>1GB</td> <td>1GB</td></tr> <tr> <td>Recommended</td> <td>2GB+</td> <td>2GB+</td>  <td>2GB+</td> </tr> </tbody> </table> <table class="Table Table--style1 Table--comparison"> <colgroup> <col width="18%" /> <col width="20%" /> <col width="28%" /> <col width="20%" /> <col width="10%" /><thead> <tr class="Table-RowDivision"> <td colspan="5"><strong>Display</strong></td> </tr> </thead> <tbody> <tr> <td>Recommended</td> <td colspan="4">1024 x 768 or higher-resolution display</td> </tr> </tbody> </table> <table class="Table Table--style1 Table--comparison"> <colgroup><col width="18%" /> <col width="20%" /> <col width="28%" /> <col width="20%" /> <col width="10%" /><thead> <tr class="Table-RowDivision"> <td colspan="5"><strong>Browser Support</strong> </td> </tr> </thead> <tbody><tr> <td>Supported</td> <td colspan="4">Internet Explorer 11, MS Edge, Chrome, Firefox and Safari, MS Edge Chromium Beta latest versions</td> </tr> </tbody> </table></div>
<br>

## User Account Control (UAC)

* User Account Control Settings set to 'Never Notify'

## Recommended Browsers

* Internet Explorer 11 (**Note**: IE 9 and 10 support is dropped as of R2 2016 release).
* Chrome latest version
* FireFox latest version
* Edge latest version
* Edge Chromium Beta latest version
* Safari latest version (5.1.7)

## Test Studio VS plugin

* IDE (Visual Studio plug-in only): Visual Studio 2012, 2013, 2015, 2017 and 2019 Professional or higher.
	
	* You must run Visual Studio as Administrator
	* Visual Studio projects should target .Net 4.5 or higher.
	* Visual Studio 2017 requires additional <a href="/general-information/installation/vs2017-compatibility" target="_blank">Individual components</a> on top of its default installation. 

## Data Binding

*	Microsoft Office installation or <a href="https://www.microsoft.com/en-us/download/details.aspx?id=23734" target="_blank">Microsoft Data Connectivity Components</a> (x86 redistributable).

## Framework

* <a href="https://www.microsoft.com/en-us/download/details.aspx?id=42642" target="_blank">.NET 4.5</a> or higher

##Supported Databases##

* MongoDB 3.0+, 4.0+ (**Note**: MongoDB requires at least 4 Gb of free space on machine where the Storage server is installed)

## Source Control

* Git

* TFS

	* Visual Studio has built-in TFS integration 

	OR

	* Test Studio Standalone version on a machine with installed: Team Explorer 2013 (Visual Studio plugin - available from a MSDN account) or supported Visual Studio version. If using product version **R2 2017 SP1** or later - no additional tools have to be installed on the machine.

## Build Server / Continuous Integration

If executing via <a href="/features/test-runners/mstest" target="_blank">MSTest</a>

* Visual Studio (see above requirements) with VS plugin, __or__

* MSTest.exe installed on agent and controller

* Test Studio Runtime or above installed on agent

If executing via <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a>

* <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Run-Time edition</a>

## Beta Software

* Operating systems and web browsers in the beta stage are not supported.
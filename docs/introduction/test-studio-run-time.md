---
title: Test Studio vs. Run-Time
page_title: Test Studio vs. Run-Time
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 5
---
<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
}
table.docs th {
color:#fff;
background-color:#00ab8e;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>

# Test Studio vs. Run-Time Edition

* <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> - develop and execute tests on one machine (per license).

* Run-Time Edition - execute tests on one machine (per license). No GUI for loading and developing tests. Intended to be installed on build servers or scheduling and execution servers.

Licensing is managed on a per machine basis. You activate a single license on one machine at a time. This includes virtual machines; Test Studio considers each VM as one machine requiring one license.

There are no restrictions on the number of users who work with Test Studio (or Run-Time edition) as long as the software is used on the licensed machine only and only one user is using the software at any given time. The floating machine license allows you to activate and deactivate the same license on multiple machines as long as you have just one activated copy at a time.

It is not possible to activate more than one license on a single machine at a time. You cannot install Test Studio and the Run-Time edition on the same machine at the same time.

## What's Included in Run-Time Edition?

<table class="docs">
<tr>
	<th>Component</th><th>Description</th>
</tr>
<tr>
	<td><b>ArtOfTest.Runner</b></td><td>Test Studio's built-in automated test execution engine. Available for use from the <a href="/features/test-runners/artoftest-runner" target="_blank">command line</a>.</td>
</tr>
<tr>
	<td><b>Telerik.TestStudio.ManualRunner</b></td><td>Test Studio's built-in automated test execution engine. Available for use from the <a href="/features/test-runners/artoftest-runner" target="_blank">command line</a>.</td>
</tr>
<tr>
	<td><b>MSBuild Add-On</b></td><td>Test Studio's built-in automated test execution engine. Available for use from the <a href="/features/test-runners/mstest" target="_blank">MSTest</a>.</td>
</tr>
<tr>
	<td><b>Browser Extensions</b></td><td>Execute tests in Internet Explorer, Firefox, Safari, and Chrome.</td>
</tr>
<tr>
	<td><b>Results Viewer</b></td><td>Someone like a manager can load and view the <i>.aiiresult</i> file (the output from a Test Studio test list run).</br> Use this program by:<br/>
	<ul>
    <li>Double click an .aiiresult file in the Results folder.</li></br>
    <li>Load it directly: <b>C:\Program Files (x86)\Telerik\Test Studio\Bin\Telerik.TestStudio.ResultsViewer.exe</b></li> 
	</ul>
</td>
</tr>
<tr>
	<td><b>Scheduling Server Utility</b></td><td>Configure machine as a <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">Scheduling Server</a> for use with Test Studio's <a href="/features/scheduling-test-runs/overview" target="_blank">Scheduling feature</a>.<br/> 
	<ul>
    <li>Launch utility: <b>Start > All Programs > Telerik > Test Execution > Configure as Scheduling Server</b></li></td>
	</ul>
</tr>
<tr>
	<td><b>Execution Server Utility</b></td><td>Configure machine as a <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution Server</a> for use with Test Studio's <a href="/features/scheduling-test-runs/overview" target="_blank">Scheduling feature</a>. <br/>
	<ul>
    <li>Launch utility: <b>Start > All Programs > Telerik > Test Execution > Configure as Execution Server</b></li>
	</ul>
</td>
</tr>
</table>

<br>

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

## Where Do I Install Run-Time Edition?


<style>
table.docs1 {
	font-family: verdana,arial,sans-serif;
	font-size:11px;
	color:#333333;
	border-collapse: collapse;
	border:none;
}
table.docs1 th {
	color:#fff;
	background-color:#00ab8e;
	border-width: 1px;
	padding: 8px;
	border-style: solid;
	border-color: #dbdbdb;
}
table.docs1 tr {
	background-color:#ffffff;
	border:none;
}
table.docs1 td {
	border:none;
	padding: 8px;
	
}
</style>
<table class="docs1">
<tr>
	<th>Test Studio Environment &nbsp;</th><th>Build Server Environment</th>
</tr>
<tr>
	<td><b>Scheduling</b>
	<ul>
	<li>Scheduling Server</li></br>
	<li>Execution Server</li>
	</ul>
	</td>     
	<td>
	<ul>
	</br>
	<li>Build Server/Agent</li></br>
	<li>Test Controller</li></br>
	<li>Test Agent</li>
	</ul>
	</td>
</tr>
<tr>
	<td><b>Performance Testing</b> </br>
	<ul>
	<li>Execution Server</li>
	</ul>
	</td>
</tr>
<tr>
	<td><b>Load Testing</b> </br>
	<ul>
	<li>Controller</li>
	<li>Reporter</li>
	<li>Agent</li>
	</td>
</tr>
</table>

<br>

## Is It Possible To Install Run-Time Using A Command Line? 

If installing Run-Time on multiple machines you could automate the process using the command line prompt.

&nbsp; &nbsp; &nbsp; `msiexec /q /i TestStudio_Runtime_[version].msi`

* The default Run-Time installation will add Scheduling and Storage services on the target machine. To skip their installation you could use the following arguments:

&nbsp; &nbsp; &nbsp; `msiexec /q /i TestStudio_Runtime_[version].msi INSTALL_SCHEDULING_SERVER=False INSTALL_STORAGE_SERVICE=False`

<br>

## How To Update The Run-Time Version?

If running tests in a scheduling configuration it is important to keep Test Studio and Run-Time versions equal to prevent possible misbehavior. Each next version of the Run-time edition could be found for download in the product license holder's Telerik account.
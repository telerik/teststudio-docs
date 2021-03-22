---
title: Troubleshooting Results Errors
page_title: Troubleshooting Results Errors
description: "Troubleshooting Results Errors from Test Studio load test run."
position: 2
---
# Troubleshooting Results Errors

Sometimes you may be faced with trying to figure out why the number of completed users is too low, possibly staying at 0 during the entire test. This is usually accompanied by the number of total HTTP errors continually rising as well. To troubleshoot this case you may need to turn on trace debugging.

This must be done manually be setting two registry keys:

![Registry][1]

- TraceLogPath - This registry key defines the path and filename where the write the trace data into. If the path and or file do not exist, Test Studio will create it for you.
- TraceLogEnabled - This registry key turns on/off tracing. Turn it on by setting the value to 1. Turn it off by setting the value to 0.

This file is a text file containing trace data. Below is a sample version of this file.

<div style="height: 200px; width: 800px; overflow: scroll; margin: 20px;">

	[03/29 17:33:27,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:27,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:32,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:32,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:37,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:37,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:38,Telerik.TestStudio.Services.exe(588:18)] First trace message from pool unnamed thread (managed ID = 18, native ID = 2944).
	[03/29 17:33:38,Telerik.TestStudio.Services.exe(588:18),Load] LoadAgentService.PingControllerAsync() : Checking to see if the controller is still active...
	[03/29 17:33:38,Telerik.TestStudio.Services.exe(588:6),WindowsServices] TestStudioSingletonServiceBase.Ping() : Command received.
	[03/29 17:33:38,Telerik.TestStudio.Services.exe(588:18),Load] LoadAgentService.PingControllerAsync() : Controller is still active.
	[03/29 17:33:42,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:42,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:45,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromClient_GetDataPointsForCounter() : Command received.
	[03/29 17:33:47,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:47,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:52,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:52,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:33:57,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:33:57,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:02,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:02,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:07,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:07,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:12,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:12,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:17,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:17,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:22,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:22,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:27,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:27,Telerik.TestStudio.Services.exe(588:6),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:32,Telerik.TestStudio.Services.exe(588:8)] First trace message from pool unnamed thread (managed ID = 8, native ID = 2376).
	[03/29 17:34:32,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:32,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:37,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:37,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:38,Telerik.TestStudio.Services.exe(588:18),Load] LoadAgentService.PingControllerAsync() : Checking to see if the controller is still active...
	[03/29 17:34:38,Telerik.TestStudio.Services.exe(588:8),WindowsServices] TestStudioSingletonServiceBase.Ping() : Command received.
	[03/29 17:34:38,Telerik.TestStudio.Services.exe(588:18),Load] LoadAgentService.PingControllerAsync() : Controller is still active.
	[03/29 17:34:42,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:42,Telerik.TestStudio.Services.exe(588:8),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:48,Telerik.TestStudio.Services.exe(588:9)] First trace message from pool unnamed thread (managed ID = 9, native ID = 2712).
	[03/29 17:34:48,Telerik.TestStudio.Services.exe(588:9),Load] LoadReporterService.FromLoadController_TestDBConnection() : Command received.
	[03/29 17:34:48,Telerik.TestStudio.Services.exe(588:9),Load] LoadReporterEntityBridge.TestDBConnection() : DB Test Successful, detected 1 versions.
	[03/29 17:34:50,Telerik.TestStudio.Services.exe(588:8),Load] LoadAgentService.FromController_AllocateScenarioGroup() : Command received.
	[03/29 17:34:50,Telerik.TestStudio.Services.exe(588:8),Load] LoadControllerService.FromClient_RunTestAsync() : Command received to run test 4595bac5-aeaa-436f-9196-c7bda3399a83.
</div>

To set these keys follow these steps:


1.&nbsp; Run **Regedit** to start the Windows Registry editor.

2.&nbsp; Navigate to the correct registry node depending on the bitness of your Windows installation. If the Telerik subnode does not exist, create it.

- 32 bit: **HKEY_USERS\.DEFAULT\Software\Telerik\Test Studio**
- 64 bit: **HKEY_USERS\.DEFAULT\Software\Wow6432Node\Telerik\Test Studio**

3.&nbsp; Add the key **TraceLogPath** as a string type.

4.&nbsp; Set its path to the desired location and file you want trace data saved to.

5.&nbsp; Add the key **TraceLogEnabled** as a DWORD type. Set its value to 1. When you want to turn off tracing, set this value to 0.

You can also use this .reg file to create the keys for you:

Windows Registry Editor Version 5.00

*[HKEY_USERS\.DEFAULT\Software\Telerik\Test Studio]<br>
"TraceLogPath"="C:\\Logs\\Log.txt"<br>
"TraceLogEnabled"=dword:00000001*

[1]: /img/features/testing-types/load-testing/troubleshooting-results-errors/fig1.png
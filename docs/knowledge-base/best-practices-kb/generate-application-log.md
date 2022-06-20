---
title: Generate Application Log
page_title: Generate Application Log
description: How to generate the Test Studio application log? The application log records all events happening in the UI and can be used when troubleshooting various errors, which appear while recording, executing tests or while maintaining the test project. Any unexpected errors can be also explored in the application log. 
position: 1
---
# How to Generate the Test Studio Application Log

Test Studio application logging records all events triggered from the tool while recording tests, executing these or maintaining elements and tests in the project. It is a powerful source of information, which helps to investigate any sort of issues.

The log is a plain text file stored in the **Logs** sub-folder under the product's installation one **C:\Program Files (x86)\Progress\Test Studio**. By default logging is disabled and if you need to generate it, you first need to enable it.

The topics in this article guides you through the different options to access the logging:

- [When to generate the application log](#when-to-generate-application-log)
- [How to generate logging in Test Studio Standalone?](#operate-with-logging-in-standalone-version)
- [How to generate logging in Test Studio Scheduling setup?](#operate-with-logging-in-scheduling-configuration)
- [How to generate logging in Test Studio Run-time Edition?](#operate-with-logging-in-run-time-edition)
- [How to generate logging in Test Studio Dev Edition (plugin for Visual Studio)?](#operate-with-logging-in-visual-studio-plugin)
- [How to generate logging in Test Studio if there is no UI available?](#enable-logging-through-the-registry-editor)

## When to Generate Application Log?

The application log is a set of records, which are useful for analyzing all sort of inconsistent behavior while working on a project in Test Studio. The application log is useful for unexpected occurrences such as:

- a crash in the product;
- unexpected termination of a test run, which might prevent generating the execution log;
- inconsistent behavior while working with the project components (Elements Explorer, Project Explorer, Properties pane, configuring/using the Source Control integration, configuring the Scheduling services, etc.);

The steps below describe the recommended approach for generating the application log so that it contains the details for the encountered error:

* Clear the log file;
* Ensure logging is enabled;
* Reproduce the misbehavior to be investigated;
* Once the observed inconsistency is present, open the application log from the _'View Log'_ option;
* The logging records are opened in a text editor file (usually Notepad);
* You can revise the logged messages yourself and try to find a solution based on the error message.
* Or you can contact the Test Studio Support Team and send the zipped log file via a support thread describing the experienced issue.

> __Tip__
><br>
><br>
> Find out more about <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log" target="_blank">using the application log</a> in our troubleshooting guide.

## Operate with Logging in Standalone Version

The logging options for the Standalone Test Studio version are listed under the _Help_ menu in the upper right corner of the project window.

1.&nbsp; Click on the **Help** drop down and choose the  **Enable Logging** option to allow Test Studio to start capturing the tool's events in the background.

![Enable log][7]

2.&nbsp; Once you enable the logging the button turns to **Disable Logging** and you can stop it at any time.

![Disable log][7a]

3.&nbsp; While logging is enabled you can access it any time by choosing the **View Log** option. The log file gets opened in Notepad and you can save or, if requested, send it for analysis.

![View log][8]

4.&nbsp; If the logging is enabled for some time the text file may become very large. Use the __Clear Log__ option to remove the records generated so far.

![Clear log][8a]

## Operate with Logging in Scheduling Configuration

<a href="/automated-tests/scheduling/overview" target="_blank">Test Studio Scheduling setup</a> allows you to connect multiple machines for test execution remotely. When such setup is configured you can find a list of all included machines in the <a href="/automated-tests/scheduling/view-execution-status" target="_blank">Execution status view</a> accessible from your local computer. From this list you can access the logging for each of the execution machines.

1.&nbsp; Open the __Execution status view__ and choose an execution machine from the list.

![Execution status view][3]

2.&nbsp; Double click on the remote machine from which you need the logging. The __Execution server details__ view provides access to the remote machine logs.

![Execution server details][4]

3.&nbsp; You have the options to enable/disable the logging, view the generated records, or clear the logging.

## Operate with Logging in Run-Time Edition

The logging options can be accessed from the Test Studio Test Runner. This is hidden in the system tray when started and gets opened from the __Show__ option from the right mouse context menu.

![Open Test Studio Test Runner](/img/features/scheduling-test-runs/create-execution-server/fig1.png)

You have the options to enable/disable the logging, view the generated records, or clear the logging.

![Logging in Test Studio Test Runner](/img/features/scheduling-test-runs/create-execution-server/fig6a.png)

## Operate with Logging in Visual Studio Plugin

The logging options in Visual Studio can be accessed through the <a href="https://docs.telerik.com/devtools/teststudiodev/features/project-settings/overview" target="_blank">Test Studio Project settings</a>. The last tab is dedicated to logs and you have access to all options - enable/disable, view and clear.

![Test Studio Logging in Visual Studio](/img/knowledge-base/best-practices-kb/generate-application-log/vs-logging.png)

## Enable Logging through the Registry Editor

Enabling the logging is actually setting a key in the registry. If you don't have access to any of the above sources, or you use the Testing Framework, you can enable the logging directly in the Windows Registry Editor.

1.&nbsp;Start <a href="http://support2.microsoft.com/kb/136393" target="_blank">Regedit</a> and browse to the Test Studio folder. The path for default installation is:

* **Computer\HKEY_CURRENT_USER\Software\Wow6432Node\Telerik\Test Studio**

![Registyry][6]

Find (or create) the _TraceLogEnabled_ key in this folder. Double click it and change the Value data to 1. You should also see the _TraceLogPath_ value. This is where the log will be stored. Ensure you include the file name and type:

* **C:\Temp\TraceLog\log.txt**

[1]: /img/knowledge-base/best-practices-kb/generate-application-log/fig1.png
[2]: /img/knowledge-base/best-practices-kb/generate-application-log/fig2.png
[3]: /img/knowledge-base/best-practices-kb/generate-application-log/fig3.png
[4]: /img/knowledge-base/best-practices-kb/generate-application-log/fig4.png
[5]: /img/knowledge-base/best-practices-kb/generate-application-log/fig5.png
[6]: /img/knowledge-base/best-practices-kb/generate-application-log/fig6.png
[7]: /img/knowledge-base/best-practices-kb/generate-application-log/fig7.png
[7a]: /img/knowledge-base/best-practices-kb/generate-application-log/fig7a.png
[8]: /img/knowledge-base/best-practices-kb/generate-application-log/fig8.png
[8a]: /img/knowledge-base/best-practices-kb/generate-application-log/fig8a.png
[9]: /img/knowledge-base/best-practices-kb/generate-application-log/fig9.png

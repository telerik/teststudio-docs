---
title: Telerik.TestStudio.CommandLineClient
page_title: Telerik.TestStudio.CommandLineClient
description: "Test Studio Scheduled runs via command line"

position: 2
---
# Telerik.TestStudio.CommandLineClient

Telerik.TestStudio.CommandLineClient is a command line execution engine for remote runs and can be used if the <a href="/features/scheduling-test-runs/remote-run-all-in-one" target="_blank">Telerik Scheduling and Storage services</a> are installed. It allows you to execute your test lists via any configured Scheduling server in your domain, distribute them across the configured execution machines in the setup and send the result via e-mail.

Telerik.TestStudio.CommandLineClient.exe is installed in your Test Studio installation directory. The default location is:

- **C:\Program Files (x86)\Telerik\Test Studio\Bin**

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

When working with the Telerik.TestStudio.CommandLineClient in the command prompt, make sure you always are running as Administrator and have the root directory in context as shown below so that you can call the runner directly.

![CMD][1]

> If you would like to call the Telerik.TestStudio.CommandLineClient.exe from any directory within the command prompt follow <a href="/features/test-runners/add-path-environment-variables" target="_blank">this article</a> on how to Add Path to Environment Variables.

## Execution Test List Options

Supported options can be viewed by calling Telerik.TestStudio.CommandLineClient.exe --help

![cmd help][2]

Execution options modify command line test list execution behavior. The help file provides a brief explanation of each option. Here are some further notes about specific options.

Several execution options use file paths as values. When using file paths in the command prompt:

- Enclose the file path in double quotes.
- To prevent typing mistakes, use the clipboard paste option within the command prompt window. To find the paste option after copying the path to the clipboard, right mouse click on the top left corner of the command prompt and choose **Edit > Paste**.

![Edit][3]

- The -**l** option takes the full path to an individual test list with the **.aiilist** file extension. This file will be located in your main project directory/TestLists and under any folder structure you have created to organize your tests. Your test project should be connected to a scheduling server. The test list will be executed on all execution machines which are connected to this scheduling server. If any of the optional parameters are not supplied, they will be either be pulled off the project, or omitted.

![L Option][4]

- The -**u** option specifies the full address (http://someserver:8009/) of the scheduling server which will be used for execution the test list. If it is skipped, it will be pulled off the project.

![U Option][5]

[1]: /img/features/scheduling-test-runs/tts-command-line-client/fig1.png
[2]: /img/features/scheduling-test-runs/tts-command-line-client/fig2.png
[3]: /img/features/scheduling-test-runs/tts-command-line-client/fig3.png
[4]: /img/features/scheduling-test-runs/tts-command-line-client/fig4.png
[5]: /img/features/scheduling-test-runs/tts-command-line-client/fig5.png
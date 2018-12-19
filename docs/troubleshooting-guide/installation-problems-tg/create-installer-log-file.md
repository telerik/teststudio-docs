---
title: Create Installer Log File
page_title: Create an Installer Log File
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Create an Installer Log File


## PROBLEM

For most users, installing the application is a breeze. The process goes through without a hiccup. For some, however, an issue is experienced at the time of install. In case the installer does not complete and provides no real error message, there is a process you can do to still generate a log of the install. This document discusses the process of generating this logfile.

## EXAMPLES

You will most likely see this issue:

- When your downloaded installer file had some form of corruption caused during download.

- If you have an incompitiblity present that is causing conflict with the installer.


Regardless of the reason for the failed install, the best feedback to get is an installer log. The below process goes over how to generate an install log file using our provided installer .msi file.

## SOLUTION

If you used the Telerik Control Panel to install Test Studio, the log was automatically generated for you. Simply open the folder %ProgramData%\Telerik\Installer\Logs and locate the appropriate log file. It will be named something like:

- msi_log_2015-11-18_TestStudio_WebDesktop_2015_3_1015_Purchase.log

Place this file into a .zip or .rar file and attach it as a file attachment to a support ticket. Once we receive the logfile, we can more easily assist with determining the root cause of the install not completing.

If you're installing using a .MSI file you will need to follow these steps to generate a MSI logfile:

1.&nbsp; Bring up a command prompt window.

  a. Click **Start > Run**.
  
  b. In the prompt, input **cmd**. 

![cmd][1]

  c. Click **OK**.

You should have a new command prompt console window open. When it opens:

2.&nbsp; Navigate to the folder that the downloaded installer file is saved within.

In the example below, the installer is contained in D:\TestStudio\ but your location on your drive may be different so make sure you are in the right folder before running the below command.

![Installers][2]

3.&nbsp; Input the following command: *msiexec /i installer.msi /limev D:\TestStudio\installer.log* 

> In the above example, replace *installer.msi* with the exact name for the installer you downloaded from telerik.

<br>

> In the above example, replace *D:\TestStudio\installer.log* with the directory path and filename you want the log saved to/as.

4.&nbsp; Once you have the above personalized as we do in the example, press the '**enter**' key on your keyboard to begin the install and generate a log. 

![Log generated][3]

5.&nbsp; After you generate the file, please compress it to either .zip or .rar format and attach it to your new or existing support ticket.   

Once we receive the logfile, we can more easily assist with determining the root cause of the install not completing.

[1]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig1.png
[2]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig2.png
[3]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig3.png

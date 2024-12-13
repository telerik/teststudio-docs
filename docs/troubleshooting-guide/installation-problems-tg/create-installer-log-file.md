---
title: Create Installer Log File
page_title: Create an Installer Log File
description: "How to create log file during the Test Studio installation process. Can an installer log be created for a failing installation?"
position: 1
---
# Create an Installer Log File


## Problem

For most users, installing the application is a breeze. The process goes through without a hiccup. For some, however, an issue is experienced at the time of install. In case the installer does not complete and provides no real error message, there is a process you can do to still generate a log of the install. This document discusses the process of generating this log file.

## Possible Causes

You will most likely see this issue:

- When your downloaded installer file had some form of corruption caused during download.

- If you have an incompatibility present that is causing conflict with the installer.


Regardless of the reason for the failed install, the best feedback to get is an installer log. The below process goes over how to generate an install log file using our provided installer .msi file.

## Troubleshoot

The most convenient approach to investigate such issues is to check the installer log and analyze the specific case.

## Generate Installer Log for Telerik Control Panel Installation

If you used the __Telerik Control Panel__ to install Test Studio, the log was automatically generated for you. Simply open the folder %ProgramData%\Progress\Installer\Logs and locate the appropriate log file. It will be named something like:

- `msi_log_2015-11-18_TestStudio_WebDesktop_xxxx_x_xxx_Purchase.log`

Place this file into a .zip file and attach it to a support ticket. Once we receive the log file, we can assist with determining the root cause of the install not completing.

## Generate Installer Log for Test Studio MSI Installer 

If you're installing using the .MSI file follow these steps to generate a MSI logfile:

1.&nbsp; Bring up a command prompt window with admin privilege.

  a. Click **Start > Run**.
  
  b. In the prompt, input **cmd**. 

![cmd][1]

  c. Click **OK**.

Open a new command prompt console window and follow the steps: 

2.&nbsp; Navigate to the folder where the downloaded installer file is saved within.

In the example below, the installer is contained in D:\TestStudio\ but your location on your drive may be different so make sure you are in the right folder before running the below command.

![Installers][2]

3.&nbsp; Input the following command:

- `msiexec /i installer.msi /limev D:\TestStudio\installer.log` 

where **installer.msi** is the exact name for the installer you downloaded from your Telerik account and __D:\TestStudio\installer.log__ is the full file name for the log to be saved.

4.&nbsp; Once you have the above personalized as we do in the example, press the **Enter** key on your keyboard to begin the install and generate a log. 

![Log generated][3]

5.&nbsp; After you generate the file, please compress it to a .zip file and send it in your new or existing support ticket.

[1]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig1.png
[2]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig2.png
[3]: /img/troubleshooting-guide/installation-problems-tg/create-installer-log-file/fig3.png

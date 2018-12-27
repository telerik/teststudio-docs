---
title: Automate ClickOnce App
page_title: Automate ClickOnce App | Test Studio Dev Documentation
description: Automate ClickOnce App
position: 5
---
# Automate "ClickOnce" WPF Application

## Problem

To automate a WPF application it is necessary to <a href="/features/recorder/record-test#Record-a-Wpf-Test" target="_blank">configure the path to the executable file</a> of the app. It is a problem when there is a WPF <a href="https://docs.microsoft.com/en-us/visualstudio/deployment/clickonce-security-and-deployment#what-is-a-clickonce-application" target="_blank">ClickOnce</a> application. Then each new version of the app is installed in a different location. Here is a possible approach to the problem where a mixed test list containing a Web and WPF test is used.

## Solution

It is necessary to create a stand alone class file (*Utility*) which static property (*pathFile*) will be used to store the path to the latest app version:

#### __[C#]__

    {{region }}

    public class Utility
    {
        public static string pathFile = string.Empty;
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Public Class Utility

        Public Shared pathFile As String = String.Empty

    End Class
    {{endregion}}

The following scenario assumes that the app is downloaded form a web destination, installed and ran from a browser. In such case the first test in the list will be a Web test that will complete the app installation part. At the end of the installation the latest app version will be up and running. This test have to end with acoded step which will save in a variable the path to the new application as given bellow:

#### __[C#]__

    {{region }}

    // check if there is running process with same name
    var runningApp = System.Diagnostics.Process.GetProcesses().Where(p => p.ProcessName == "YourClickOnceWpfApp");

    // get the process
    var proc = runningApp.FirstOrDefault();

    // log the name of the process to the Execution Log
    Log.WriteLine(proc.MainModule.FileName.ToString());

    // save the full path to a common variable
    Utility.pathFile = proc.MainModule.FileName.ToString();
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim runningApp = System.Diagnostics.Process.GetProcesses().Where(Function(p) p.ProcessName = "YourClickOnceWpfApp")

    Dim proc = runningApp.FirstOrDefault()

    Log.WriteLine(proc.MainModule.FileName.ToString())

    Utility.pathFile = proc.MainModule.FileName.ToString()

    {{endregion}}

Next step is to create a WPF test that begins with a coded step and is configured to run a dummy WPF app. In the coded step the initially started mock app will be closed. Then depending on the latest version state (running/stoped) Test Studio will connect to or open it for next test steps execution:

#### __[C#]__

    {{region }}

    // Shut down "mock" app
    ActiveApplication.Quit();

    // check if there is running process with same name
    var runningApp = System.Diagnostics.Process.GetProcesses().Where(p => p.ProcessName == "YourClickOnceWpfApp");

    // if there is same app running - connect to it
    if (runningApp.Count() != 0)
    {
        Manager.ConnectToApplication(runningApp.FirstOrDefault());
    }
    else
    {
        // or - launch new application
        Manager.LaunchNewApplication(Utility.pathFile);
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    ActiveApplication.Quit()

    Dim runningApp = System.Diagnostics.Process.GetProcesses().Where(Function(p) p.ProcessName = "YourClickOnceWpfApp")

    If runningApp.Count() <> 0 Then

        Manager.ConnectToApplication(runningApp.FirstOrDefault())

    Else

        Manager.LaunchNewApplication(Utility.pathFile)

    End If

    {{endregion}}
---
title: Connect to Running App
page_title: Connect to Running App | Test Studio Dev Documentation
description: Connect to Running App
position: 1
---
# Connect to a Running WPF Application #

*I would like to connect to an already running WPF application and execute the test there, instead of launching a new instance of the app.*

##Solution##

When you Quick Execute or execute a Test List, a new instance of the app launches from its pre-configured location.

To work around this limitation, create a mock application to feed to Test Studio. Then insert a coded step as the first step of the test. Use the following code which closes the mock application and connects to the desired application if it's running. If not, a new instance is launched.

#### __[C#]__

    {{region }}

    ActiveApplication.Quit();
    var runningApp = System.Diagnostics.Process.GetProcesses().Where(p => p.ProcessName == "WPFHelloWorld");
    
    if (runningApp.Count() != 0)
    {
        Manager.ConnectToApplication(runningApp.FirstOrDefault());
    }
    else
    {
        Manager.LaunchNewApplication(@"C:\ApplicationFolder\WPFHelloWorld.exe");
    }
    
    Manager.ActiveApplication.MainWindow.RefreshVisualTrees();
    {{endregion}}

#### __[VB]__

    {{region }}

    ActiveApplication.Quit()
    Dim runningApp = System.Diagnostics.Process.GetProcesses().Where(Function(p) p.ProcessName = "WPFHelloWorld")
    
    If runningApp.Count() <> 0 Then
        Manager.ConnectToApplication(runningApp.FirstOrDefault())
    Else
        Manager.LaunchNewApplication("C:\ApplicationFolder\WPFHelloWorld.exe")
    End If
    
    Manager.ActiveApplication.MainWindow.RefreshVisualTrees()
    {{endregion}}
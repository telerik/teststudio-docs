---
title: Override app.config
page_title: Override app.config
description: "Override Test Studio app.config to get tue run-time configuration settings in Visual Studio."
position: 1
---
#Override the app.config File in a Test Studio Project#

*I would like Visual Studio to load the app.config file to get its run-time configuration settings.*

##Solution##

> The app.config only applies to projects in Visual Studio as expained <a href="http://msdn.microsoft.com/en-us/library/a65txexh.aspx" target="_blank">here</a>.

The concept is that you can place application configuration settings in the app.config file (like user ID, connection strings, etc.) and have the application load this config file to get its run-time configuration settings. In <a href="https://docs.microsoft.com/en-us/visualstudio/ide/use-solution-explorer?view=vs-2019" target="_blank">Solution Explorer</a> it will show as app.config. When you compile the project it gets renamed and placed in the **projectFolder\bin\debug **or **projectFolder\bin\release** folder alongside your application (.exe) file. So if your application file is named **MySpecialApp.exe**, next to it will be **MySpecialApp.exe.config**.
 
However, this doesn't work with a default Test Studio project. A Test Studio project builds to a DLL file. This DLL file is then executed by Test Studio's test runner. The reason that test project ignores the app.config file is because the test runner is the application and the test runner is going to load its own app.config file. It's going to ignore the app.config file that belongs to the DLL being tested. In order to work around this, you need to expressly write a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to find it, open it, read it and parse it. We have a sample below that demonstrates how this is done. In order to make this code work, <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to the following assemblies:

* *System.Reflection*

* *System.Configuration*

```C#
Assembly me = Assembly.GetExecutingAssembly();
Configuration config = ConfigurationManager.OpenExeConfiguration(me.ManifestModule.Assembly.Location);
  
string url = config.AppSettings.Settings["LoginPageUrl"].Value;
string name = config.AppSettings.Settings["LoginName"].Value;
string pw = config.AppSettings.Settings["Pass"].Value;
string UserId = config.AppSettings.Settings["UserId"].Value;
string conn = config.ConnectionStrings.ConnectionStrings["ConnectionString"].ConnectionString;
```
```VB
Dim [me] As Assembly = Assembly.GetExecutingAssembly()
Dim config As Configuration = ConfigurationManager.OpenExeConfiguration([me].ManifestModule.Assembly.Location)
 
Dim url As String = config.AppSettings.Settings("LoginPageUrl").Value
Dim name As String = config.AppSettings.Settings("LoginName").Value
Dim pw As String = config.AppSettings.Settings("Pass").Value
Dim UserId As String = config.AppSettings.Settings("UserId").Value
Dim conn As String = config.ConnectionStrings.ConnectionStrings("ConnectionString").ConnectionString
```
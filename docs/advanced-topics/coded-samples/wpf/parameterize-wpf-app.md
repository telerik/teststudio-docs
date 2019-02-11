---
title: Parameterize WPF App
page_title: Parameterize WPF App
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/wpf/parameterize-wpf-app-location.aspx, /user-guide/code-samples/wpf/parameterize-wpf-app-location
position: 2
---
#Parameterize the Location of a WPF Application#

Currently Test Studio is rigged that you cannot run a WPF Test unless you provide a definite (non-parameterized) location for the application under testing.

![Configure WPF path][1]

##Solution##

To work around this limitation, create a mock application to feed to Test Studio. Then change the application under testing in a coded step. This allows you to use a parameterization method of your choosing for the app's location. This solution is applicable for both Test Studio Standalone version and the Visual Studio plugin.

1.&nbsp; Create a mock WPF Application. The content of the application is irrelevant. Its location needs to be permanent.

2.&nbsp; Record a WPF Test against your "real" application

3.&nbsp; Now configure the WPF Application Path for your test (see screenshot above) to point to the location of the mock application created in step 1.

4.&nbsp; Add a Coded Step to the test and move it to be the first step. In this coded step, define the logic that will shut down the default (mock) app, then start and connect to the "real" app.

Let's assume that the "real" application is in the following location: **C:\myapps\Go.exe**. Here's the code:

```C#
//Shut down "mock" app
ActiveApplication.Quit();
 
//Define path for the "real" app. You can parameterize the location (the String argument) in a variety of ways
var pinfo = new System.Diagnostics.ProcessStartInfo(@"C:\Go.exe");

// set if any argumets are needed
pinfo.Arguments = " firstArgument secondArgument";

pinfo.Verb = "Open";
pinfo.WorkingDirectory = @"C:\";
 
//We launch the "real" app
WpfApplication app = Manager.LaunchNewApplication(pinfo);
 
//Check whether we connected successfully
Assert.IsNotNull(app);
```
```VB
ActiveApplication.Quit()
 

Dim pinfo = New System.Diagnostics.ProcessStartInfo("C:\Go.exe")

pinfo.Arguments = " firstArgument secondArgument";
pinfo.Verb = "Open"
pinfo.WorkingDirectory = "C:\"

Dim app As WpfApplication = Manager.LaunchNewApplication(pinfo)
 

Assert.IsNotNull(app)
```


You can extend this code to include parameterization for the app's location. You can use data binding, for instance. Let's say your test is bound to a data sheet with a column named "paths":


```C#
var pinfo = new System.Diagnostics.ProcessStartInfo(Data["paths"]);
```


Of course this is only one of the possible solutions you can implement. If you need to use additional assemblies, <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">here</a> is how to do that in the Standalone version.

[1]: /img/advanced-topics/coded-samples/wpf/parameterize-wpf-app/fig1.png


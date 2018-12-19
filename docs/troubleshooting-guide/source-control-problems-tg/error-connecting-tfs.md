---
title: Error Connecting to TFS Server
page_title: Error connecting to TFS server - Team Foundation services are not available from server [url]
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Error connecting to TFS server: Team Foundation services are not available from server [url]

## PROBLEM

Specific machines might fail to connect to Team Foundation Service with the error: "TF400813: Resource not available for anonymous access. Client authentication required".

![Error][1]

The error like this appears in the application log: 

<pre>
TFSServer.ConnectToServer() : EXCEPTION! (see below)
     Situation: Exception connecting to TFS server
     Outer Exception Type: Microsoft.TeamFoundation.TeamFoundationServiceUnavailableException
     Message: Team Foundation services are not available from server [url].
          Technical information (for administrator):
          TF400813: Resource not available for anonymous access. Client authentication required.
</pre>

# SOLUTION

You need to install <a href="https://visualstudiogallery.msdn.microsoft.com/f30e5cc7-036e-449c-a541-d522299445aa" target="_blank">Team Foundation Server 2012 Object Model Installer</a> and <a href="http://www.microsoft.com/en-us/download/details.aspx?id=29082" target="_blank">Visual Studio 2010 SP1 Team Foundation Server Compatibility GDR</a>.

[1]: /img/troubleshooting-guide/source-control-problems-tg/error-connecting-tfs/fig1.png
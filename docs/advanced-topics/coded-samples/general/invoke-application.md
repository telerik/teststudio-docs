---
title: Invoke Application
page_title: How to Invoke an Application
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#How to Invoke an Application#

I want to invoke a desktop application (i.e. an .exe file) from a test step.

##Solution##

You can write your own code in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> that triggers the application you need. Here's a simple example taken from <a href="http://www.csharp-station.com/HowTo/ProcessStart.aspx" target="_blank">this article</a>:

```C#
System.Diagnostics.Process notePad = new System.Diagnostics.Process();
notePad.StartInfo.FileName   = "notepad.exe";
notePad.StartInfo.Arguments = @"c:\myText.txt";
notePad.Start();
```

```VB
Dim notePad As New System.Diagnostics.Process()
notePad.StartInfo.FileName = "notepad.exe"
notePad.StartInfo.Arguments = "c:\myText.txt"
notePad.Start()
```

* In the above sample, **C:\myText.txt** is the argument fed to **notepad.exe**. If you want to test this sample code, you'll need to create this file on your local disk first. Otherwise, the notepad application will throw a *file can't be found* error.

* You can also run batch files from a coded step in the same manner.

* Alternatively, you can use a custom .NET assembly in Test Studio Standalone as seen <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">here</a>.

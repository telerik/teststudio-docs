---
title: Invoke Application
page_title: How to Invoke an Application - Test Studio Dev Documentation
description: How to Invoke an Application
position: 1
---
#How to Invoke an Application#

I want to invoke a desktop application (i.e. an .exe file) from a test step.

##Solution##

You can write your own code in a <a href="/code-in-test/features-in-code#Coded-Step" target="_blank">coded step</a> that triggers the application you need. Here's a simple example taken from <a href="http://www.csharp-station.com/HowTo/ProcessStart.aspx" target="_blank">this article</a>:

#### __[C#]__

    {{region }}

    System.Diagnostics.Process notePad = new System.Diagnostics.Process();
    notePad.StartInfo.FileName   = "notepad.exe";
    notePad.StartInfo.Arguments = @"c:\myText.txt";
    notePad.Start();
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim notePad As New System.Diagnostics.Process()
    notePad.StartInfo.FileName = "notepad.exe"
    notePad.StartInfo.Arguments = "c:\myText.txt"
    notePad.Start()
    {{endregion}}

* In the above sample, **C:\myText.txt** is the argument fed to **notepad.exe**. If you want to test this sample code, you'll need to create this file on your local disk first. Otherwise, the notepad application will throw a *file can't be found* error.

* You can also run batch files from a coded step in the same manner.


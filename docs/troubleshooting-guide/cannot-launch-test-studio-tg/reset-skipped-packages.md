---
title: Reset Skipped Packages
page_title: Reset Skipped Packages
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: false
---
# Reset Skipped Packages


## PROBLEM

In most scenarios, after installing the Test Studio VS plugin, you should not have an issue with the installed software. If Test Studio states it installed successfully, then the full suite of software should be available so long as you are licensed to use it. It is possible, through changing settings and other means, to disable an extension in Visual Studio that is used by Test Studio. When this occurs, you will most likely receive a "Package Load Failure".


## SOLUTION

If you are directed by Telerik Support, or if you are troubleshooting on your own an issue with packages not loading properly, the below steps go through the basic process of Resetting Skipped Packages:

1.&nbsp; Open a Command Prompt Console Window: 
  
  a. Click **Start > Run**.

  b. In the prompt, type *cmd* and press **Enter**. 

![cmd][1]

2.&nbsp; Navigate to your Visual Studio IDE folder (the default location for the installation of Visual Studio). 

![IDE][2]

- **VS 2010**: Default Directory is **C:\Program Files\Microsoft Visual Studio 10.0\Common7\IDE\** 

- **VS 2012**: Default Directory is **C:\Program Files\Microsoft Visual Studio 11.0\Common7\IDE\** 

- **VS 2013**: Default Directory is **C:\Program Files\Microsoft Visual Studio 12.0\Common7\IDE\** 

> Your directory may differ from the above. If it does, please use navigate to the directory that contains your devenv.exe file.

3.&nbsp; Type in *devenv /ResetSkipPkgs* at the command prompt.

![Reset][3]

4.&nbsp; Press the **Enter** key.

5.&nbsp; Allow Visual Studio some time to process the command. After it completes you should have access to your Telerik Tools once again. 

[1]: /img/troubleshooting-guide/cannot-launch-test-studio-tg/reset-skipped-packages/fig1.png
[2]: /img/troubleshooting-guide/cannot-launch-test-studio-tg/reset-skipped-packages/fig2.png
[3]: /img/troubleshooting-guide/cannot-launch-test-studio-tg/reset-skipped-packages/fig3.png
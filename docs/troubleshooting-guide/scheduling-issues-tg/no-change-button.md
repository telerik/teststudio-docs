---
title: No Change Button
page_title: No Change Button in Test Runner GUI
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# No Change Button in Test Runner GUI

## PROBLEM

 When configuring an Execution Server to connect to a Scheduling Server, no Change button appears in the Test Studio Test Runner GUI. 


## SOLUTION

**Update Client Config File**

1.&nbsp; Open the Test Studio Scheduling Client configuration file at: C:\Program Files (x86)\Telerik\Test Studio\Bin\Telerik.TestStudio.Scheduling.Client.exe.Config.xml

> Please note that as of version **2017 R3** the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

2.&nbsp; Change the EmbedExecutionManager value to false.

3.&nbsp; Close the Test Studio Test Runner process from the System Tray.

4.&nbsp; Run the Start Execution Manager application from the Start Menu.

5.&nbsp; Open the Test Studio Test Runner GUI from the System Tray.

The **Change** button should now appear on the right.


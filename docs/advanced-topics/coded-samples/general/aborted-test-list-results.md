---
title: Record Results for Aborted Test List
page_title: Record Results for Aborted Test List
description: "Record Results for Aborted Test List in Test Studio."
position: 1
---
# Record results even if test list execution is aborted #

*I would like to have results file for the already executed tests if the test list execution is aborted at an earlier stage.*

## Solution ##

Test Studio has the ability to store run results on each executed step and this could be turned on within the ***Telerik.TestStudio.Desktop.exe.config*** file. For the default installation, the file could be found in the following folder: *C:\Program Files (x86)\Telerik\Test Studio\Bin*. Open the file in a text editor and set the **'PersistOnEachStep'** key value to True.

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

```XML
  <appSettings>
      <add key="CommandLineRun" value="True" />
      <add key="PersistOnEachStep" value="False" />
  </appSettings>
```

## Command line runner arguments ##

If you execute tests from <a href="/features/test-runners/artoftest-runner" target="_blank">the command line runner</a> you could set that value to "true" by passing an argument to the command to be executed. The 'PersistOnEachStep' is one of the general options available for modifying the command line test execution behavior. 

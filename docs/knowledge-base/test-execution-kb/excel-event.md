---
title: Executing a Test from an Excel Event
page_title: Executing a Test from an Excel Event
description: Executing a Test from an Excel Event. Execute Test Studio tests or test lists by triggering events in an Excel spreadsheet
position: 1
---
#Executing a Test from an Excel Event#

Some users may want to execute Test Studio tests or test lists by triggering events in an Excel spreadsheet. For example, your goal may be to create an Excel spreadsheet with a button whose click event is attached to a macro that runs your Test Studio tests.

This is possible if you write an Excel macro to run <a href="/features/test-runners/artoftest-runner" target="_blank">the ArtOfTestRunner.exe</a> command from the command line, along with any necessary arguments. 

You will need to <a href="https://support.office.com/en-us/article/Add-a-button-and-assign-a-macro-to-it-in-a-worksheet-d58edd7d-cb04-4964-bead-9c72c843a283?ui=en-US&rs=en-US&ad=US" target="_blank">add a button control from the Developer Menu in Excel and associate it with a new macro</a>.

![Excel button][1]

In order to execute such a macro properly, Excel must be run as administrator. The Macro should use the Shell() function to execute ArtOfTest.Runner.exe with the appropriate arguments. For example:
**Call Shell("ArtOfTest.Runner.exe test=""C:\Users\landry\Documents\Test Studio Projects\TestProject119\WebTest.tstest""" & dosCmd, vbNormalFocus)**
 
Note the use of double quotes around the test location argument to ArtOfTest.Runner.exe.


![Call Shell][2]

[1]: /img/knowledge-base/test-execution-kb/excel-event/fig1.png
[2]: /img/knowledge-base/test-execution-kb/excel-event/fig2.png
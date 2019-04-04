---
title: Using BaseURL
page_title: Using BaseURL
description: Using BaseURL in a Test Studio project. Multiple test environments in which to execute test scripts. The server URL is different for each environment. How can I avoid rewriting all of my tests from scratch to make them work with a different server URL?
position: 1
---
#Running a Test Against Multiple Environments (Using BaseURL)#

I have multiple test environments in which to execute my test scripts. The server URL is different for each environment. How can I avoid rewriting all of my tests from scratch to make them work with a different server URL?

##Solution##

Test Studio allows you to create URL-relative tests with the concept of BaseURL. The BaseURL property is the static part of the URL that is set as a global setting for your entire project. A simple example is if your application **MyApplication** is deployed on both a production server **http://Server1** and a testing server **http://Server2**. If you <a href="/knowledge-base/test-execution-kb/base-url#Project-Property">set the global project setting</a> and start recording, the navigation step will be recorded as follows: 

If the application URL is **http://Server1/MyApplication** the step will be recorded as **Navigate to: '/MyApplication'** - the navigated base URL matches the global project setting and is not listed in the step.Changing the BaseURL in the project settings allows you to use the same test against the other server as well. 

In addition test lists have their own BaseURL property. This property is inherited by the project settings by default, but you could <a href="/knowledge-base/test-execution-kb/base-url#Test-Lists-Property">change it</a> to run the same tests against different servers. Bear in mind that if a test list has a BaseURL set it overrides the project property. 

##Standalone version##

###Project Property###
1.&nbsp;Click on the navigate step in your test and in the ribbon will appear the field to set the BaseURL 

![BaseURL][2]
###Test Lists Property###
1.&nbsp;To set the property for a test lists go to the **Test Lists** tab and create a new test list. Now click on **Edit Settings** and set the **BaseURL** for this test list. 

![Edit Settings][3]

2.&nbsp;In the Edit Test List Settings menu click the Web tab and find the BaseURL property 

![Base URL Test List][4]

You can create multiple test lists and set each to run against different BaseURL.

###Test Step Property###

Each navigation step has the BaseURL and NavigateURL properties. If the project has BaseURL set, the NavigationURL will look similar to: 

![Step property base URL][7]

Once the navigated URL matches the project BaseURL only the relative part is recorded to the step property. 

If the navigated URL differs from the project BaseURL the navigation step is recorded as if no additional settings are changed. 

![Step property base URL][11]

##Visual Studio  plugin##

Set the **BaseURL** from the  **Project Settings** menu just like in the Standalone version. Locate this button in the toolbar:

![VS project settings][5]

In the VS Plugin you'll need to create different test settings files for each test list. Then you can execute your test lists with MSBuild and feed them the correct test settings file as an MSBuild parameter. You can also execute a test list with a custom test settings file from the command line using <a href="/features/test-runners/MSTest" target="_blank">MSTest</a>.

To create a custom Test Settings file:

1.&nbsp;Open the Local.testsettings file.

2.&nbsp;Click Telerik Test Studio on the left and then the Web tab.

3.&nbsp;Locate the BaseURL property under the Navigation heading.

4.&nbsp;Click "Save As" rather than "Apply" to save this file under a new name.

5.&nbsp;You can now use this newly created Test Settings file.

![VS project settings][6]



##UsesBaseUrlHost##

When a recorded test step interacts with an element inside an iFrame, by default that iFrame is mapped with its full URL. There is an option, however, to specify that the URL of the iFrame is relative to the BaseURL. Highlight the Frame node in the Elements Pane and locate the **UsesBaseUrlHost** setting in the Properties Pane.
 
Let's say we want to run a test against the same application, but on different servers: **http://Server1/myApp** and **http://Server2/myApp**. Also say there's an iFrame in the app with the following source: **http://Server1/myApp/frame1.aspx**. Simply set the frame's **UsesBaseUrlHost** property to True. When you switch the BaseURL before executing the test, Test Studio will automatically swap the BaseURL portion for the frame under the hood.

![UsesBaseUrlHost][8]

When set to True, the frame uses the host portion of the project's BaseURL setting.

##FrameInfo BaseURL##

Let's say we want to run a test against the same application, but under different paths on the same server: **http://Server1/Dev1/Folder1/** and **http://Server1/Dev2/Folder1/**.
 
Modify the **BaseURL** property under **FrameInfo**. Start with '^/' to substitute the test's **BaseURL** in place of the caret (^). In this case the test's **BaseURL** defined in the **Project Settings** would be **http://Server1/Dev1** or **http://Server1/Dev2**.

![FrameInfo BaseURL][9]

##Connect to a dialog using BaseURL##

If **the base URL** of the dialog matches the one set as a **BaseUrl** property - Test Studio will automatically split the recorded URL, as well. For example - **PopupUrl** property of the "Connect to pop-up window" test step will contain the second part of the dialog's URL.

![FrameInfo BaseURL][10]


[2]: /img/knowledge-base/test-execution-kb/base-url/fig1.png
[3]: /img/knowledge-base/test-execution-kb/base-url/fig3.png
[4]: /img/knowledge-base/test-execution-kb/base-url/fig4.png
[5]: /img/knowledge-base/test-execution-kb/base-url/fig5.png
[6]: /img/knowledge-base/test-execution-kb/base-url/fig6.png
[7]: /img/knowledge-base/test-execution-kb/base-url/fig7.png
[8]: /img/knowledge-base/test-execution-kb/base-url/fig8.png
[9]: /img/knowledge-base/test-execution-kb/base-url/fig9.png
[10]: /img/knowledge-base/test-execution-kb/base-url/fig10.png
[11]: /img/knowledge-base/test-execution-kb/base-url/fig11.png
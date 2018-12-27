---
title: Using BaseURL
page_title: Using BaseURL  | Test Studio Dev Documentation
description: Test Studio Dev allows you to reuse the recorded tests against different environments following the same URL pattern - production, testing, live, etc. 
position: 0
---
# Running a Test Against Multiple Environments

If you have multiple test environments to execute automated tests against which differs only in their server URL you could reuse the automated tests for one of the environments across the rest.

Test Studio Dev allows you to create URL-relative tests with the concept of BaseURL. The BaseURL property is the static part of the URL that is set as a global setting for your entire project. A simple example is if your application **MyApplication** is deployed on both a production server **http://Server1** and a testing server **http://Server2**. If you <a href="/features/project-settings/recording-options" target=blank>set the global project setting</a> and start recording, the navigation step will be recorded as follows:

If the application URL is **http://Server1/MyApplication** the step will be recorded as **Navigate to: '/MyApplication'** - the navigated base URL matches the global project setting and is not listed in the step.Changing the BaseURL in the project settings allows you to use the same test against the other server as well. 

## UsesBaseUrlHost

When a recorded test step interacts with an element inside an iFrame, by default that iFrame is mapped with its full URL. There is an option, however, to specify that the URL of the iFrame is relative to the BaseURL. Highlight the Frame node in the Elements Pane and locate the **UsesBaseUrlHost** setting in the Properties Pane.

Let's say we want to run a test against the same application, but on different servers: **http://Server1/myApp** and **http://Server2/myApp**. Also say there's an iFrame in the app with the following source: **http://Server1/myApp/frame1.aspx**. Simply set the frame's **UsesBaseUrlHost** property to True. When you switch the BaseURL before executing the test, Test Studio will automatically swap the BaseURL portion for the frame under the hood.

![UsesBaseUrlHost][1]

When set to True, the frame uses the host portion of the project's BaseURL setting.

## FrameInfo BaseURL

Let's say we want to run a test against the same application, but under different paths on the same server - **http://Server1/Dev1/Folder1/** and **http://Server1/Dev2/Folder1/**.

Modify the **BaseURL** property under **FrameInfo**. Start with '^/' to substitute the test's **BaseURL** in place of the caret (^). In this case the test's **BaseURL** defined in the **Project Settings** would be **http://Server1/Dev1** or **http://Server1/Dev2**.

![FrameInfo BaseURL][2]

## Connect to a dialog using BaseURL

If **the base URL** of the dialog matches the one set as a **BaseUrl** property - Test Studio will automatically split the recorded URL, as well. For example - **PopupUrl** property of the "Connect to pop-up window" test step will contain the second part of the dialog's URL.

![FrameInfo BaseURL][3]

[1]: images/base-url/fig1.png
[2]: images/base-url/fig2.png
[3]: images/base-url/fig3.png

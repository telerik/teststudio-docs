---
title: Using BaseURL
page_title: Running a Test against Multiple Environments Using BaseURL
description: Using BaseURL in a Test Studio project. Multiple test environments in which to execute test scripts. The server URL is different for each environment. How can I avoid rewriting all of my tests from scratch to make them work with a different server URL? Run the same tests against the different staging environments.
position: 1
---
# Running a Test Against Multiple Environments (Using BaseURL) #

I have multiple test environments against which to execute my test scripts. The server URL is different for each environment. How can I avoid rewriting all of my tests from scratch to make them work with a different server URL?

## Solution ##

Test Studio allows you to create URL-relative tests with the concept of BaseURL. The BaseURL property is the static part of the URL that is set as a global setting for your entire project. A simple example is if your application **MyApplication** is deployed on both a production server **http://Server1** and a testing server **http://Server2**. If you <a href="#project-property">set the global project setting</a> and start recording, the navigation step will be recorded as follows:

- the project BaseURL is set to **http://Server1**.
- to start the test recording you navigate to **http://Server1/MyApplication**.
- the Navigate step will be recorded as **Navigate to: '/MyApplication'** - the navigated base URL matches the global project setting and is listed in the step under BaseUrl; the specific URL to navigate to is listed under NavigateURL property of the step.
- changing the BaseURL in the project settings allows you to use the same test against the other server as well.

In addition test lists have their own BaseURL property. This property is by default inherited by the project settings, but you can <a href="#test-lists-property">change it</a> to run the same set of tests against different servers. Bear in mind that if a test list has a BaseURL set it overrides the project property.

## Project Property ##

1. The global project setting can be set in the <a href="/features/project-settings/recording-options" target="_blank">Project Settings in the Recording tab</a>.
1. The same setting can be quick accessed in the **Test** ribbon in the **Base URL** text field.

    ![BaseURL][1]

## Test Lists Property ##

By default the test list, created in the project with already set BaseURL, inherits the same BaseURL. This can be changed in the <a href="/general-information/test-execution/test-list-settings" target="_blank">test list settings</a>. The BaseURL setting is listed under the Web tab.

![Base URL Test List][2]

> __Note!__ The test list setting overrides the project setting, and thus you can create multiple test lists and set each to run against different BaseURL.

## Test Step Property ##

When the test uses any URL, which matches the BaseURL set for the project, the Navigate step will be recorded with the URL divided accordingly in the __BaseURL__ and __NavigateURL__ - this matches the relative part of the used URL.

![Step property base URL][3]

If the navigated URL differs from the project BaseURL the navigation step is recorded as if no additional settings are changed.

![Step property base URL differs from project][4]

> __Note!__ The Navigate step overrides both the project and the test list BaseURL setting. Thus, if you need a single test to use different URL, adjust its Navigate step to use that desired URL.

## Project Property in the Visual Studio Plugin ##

The default Test Studio settings are not applied in Visual Studio when executing tests through the <a href="/general-information/test-execution/vs-2012-test-explorers" target="_blank">Test Explorer</a>. To be able to set __BaseURL__ you will need to <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">add a settings file and set it to be used from the Visual Studio Test Explorer</a>. Modify the newly created settings file to use the desired BaseURL in its Web tab.

## Using the BaseURL with Frames ##

When a recorded test step interacts with an element inside an iFrame, by default that iFrame is mapped with its full URL. There is an option, however, to specify that the URL of the iFrame is relative to the set BaseURL. Highlight the <a href="/general-information/test-recording/frames" target="_blank">Frame node</a> in the Elements Explorer and locate the **UsesBaseUrlHost** setting in the Frame's Properties Pane.

Let's say we want to run a test against the same application, but on different servers: **http://Server1/myApp** and **http://Server2/myApp**. Also say there's an iFrame in the app with the following source: **http://Server1/myApp/frame1.aspx**. Simply set the frame's **UsesBaseUrlHost** property to True. When you switch the BaseURL before executing the test, Test Studio will automatically swap the BaseURL portion for the frame under the hood.

![UsesBaseUrlHost][5]

When **UsesBaseUrlHost** is set to True, the frame uses the host portion of the project's or test list's BaseURL setting.

### FrameInfo BaseURL ###

Let's say we want to run a test against the same application, but under different paths on the same server: **http://Server1/Dev1/Folder1/** and **http://Server1/Dev2/Folder1/**.

Modify the **BaseURL** property under **FrameInfo**. Start with '^/' to substitute the test's **BaseURL** in place of the caret (^). In this case the test's **BaseURL** defined in the **Project Settings** would be **http://Server1/Dev1** or **http://Server1/Dev2**.

![FrameInfo BaseURL][6]

## Connect to a Popup Window Using BaseURL ##

If **the base URL** of the dialog matches the one set as a **BaseUrl** property - Test Studio will automatically split the recorded URL, as well. For example - **PopupUrl** property of the "Connect to pop-up window" test step will contain the second part of the dialog's URL.

![Connect to Popup with BaseURL][7]

## Maintain Previously Recorded Elements ##

If you decide to apply the BaseURL setting for the project when there are already existing tests and elements, you may need to <a href="/knowledge-base/project-configuration-kb/merge-page-nodes" target="_blank">refactor the elements</a> in the Elements Repository to adjust the Page nodes properties to reflect the <a href="/features/project-settings/recording-options#elements-page-compare-mode" target="_blank">BaseURL recording options</a>.

[1]: /img/knowledge-base/test-execution-kb/base-url/fig1.png
[2]: /img/knowledge-base/test-execution-kb/base-url/fig2.png
[3]: /img/knowledge-base/test-execution-kb/base-url/fig3.png
[4]: /img/knowledge-base/test-execution-kb/base-url/fig4.png
[5]: /img/knowledge-base/test-execution-kb/base-url/fig5.png
[6]: /img/knowledge-base/test-execution-kb/base-url/fig6.png
[7]: /img/knowledge-base/test-execution-kb/base-url/fig7.png
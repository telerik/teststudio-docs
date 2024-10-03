---
title: Launch Application
page_title: Launch Application
description: "Launch an application during the test run. Use 'Connect to application' step to connect to the running process of the desktop application to allow Test Studio to automate the application."
position: 3
---
# Launch Application

The __Launch Application__ feature allows you to define the application to automate during the test run instead of using predefined configuration. 

This article demonstrates how to add this type of step into the test.

Choose the __Launch Application__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Launch Application step][1]

There are few notable properties of the step:

- __App Path__ - defines the full file path to the application executable file.
- __Startup Arguments__ - (optional) defines startup arguments.
- __Working Folder__ - (optional) defines a working folder for desktop app. 

![Launch Application step properties][2]

> Use the <a href="/features/custom-steps/desktop-common/connect-to-app" target="_blank">'Connect to Application' step</a> to connect the test recording and execution process to the already started desktop application.

[1]: /img/features/custom-steps/launch-app/launch-app-step.png
[2]: /img/features/custom-steps/launch-app/step-launch-app-properties.png

---
title: Launch WPF Application
page_title: Launch WPF Application
description: "Launch a WPF application during the test run. Use 'Connect to WPF application' step to connect to the running WPF process to allow Test Studio to automate the application."
position: 3
---
# Launch WPF Application

The __Launch WPF Application__ feature allows you to define the application to automate during the test run instead of using predefined configuration. 

This article demonstrates how to add this type of step into the test.

Choose the __Launch WPF Application__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Launch WPF Application step][1]



There are few notable properties of the step:

- __App Path__ - defines the full file path to the application executable file.
- __Startup Arguments__ - (optional) defines startup arguments.
- __Working Folder__ - (optional) defines a working folder for WPF app. 

![Launch WPF Application step properties][2]

> Use the <a href="/features/custom-steps/wpf-common/connect-to-wpf-app" target="_blank">'Connect to WPF Application' step</a> to connect the test recording and execution process to the already started desktop application.

[1]: /img/features/custom-steps/launch-app/launch-wpf-app-step.png
[2]: /img/features/custom-steps/launch-app/step-launch-wpf-app-properties.png

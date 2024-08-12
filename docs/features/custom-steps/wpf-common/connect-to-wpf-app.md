---
title: Connect to WPF Application
page_title: Connect to WPF Application
description: "How to connect to a running WPF process in Test Studio Desktop test? Can use an already started WPF application to connect to and continue recording steps in the desktop test>"
position: 3
---
# Connect to WPF Application

The __Connect to WPF Application__ feature allows you to connect the test recording and execution process to an already started WPF application.

This article demonstrates how to add this type of step into the test.

Choose the __Connect to WPF Application__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Connect to WPF Application step][1]

There are few notable properties of the step:

- __Process Name__ - (required) defines the process to connect to.
- __Process Index__ - (optional) defines the index of the application process.
- __Set Focus__ - sets focus on the application when launched.
- __Auto Close__ - closes the application process when test completes.

![Connect to Application step properties][2]

[1]: /img/features/custom-steps/connect-to-app/step-builder-connect-app-wpf.png
[2]: /img/features/custom-steps/connect-to-app/extended-menu-connect-app.png

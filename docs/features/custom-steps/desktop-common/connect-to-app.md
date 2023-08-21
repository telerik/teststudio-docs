---
title: Connect to Application
page_title: Connect to Application
description: "How to connect to a running process of a desktop application in Test Studio Desktop test? Can use an already started application to connect to and continue recording steps in the desktop test>"
position: 2
---
# Connect to Application

The __Connect to Application__ feature allows you to connect the test recording and execution process to an already started desktop application.

This article demonstrates how to add this type of step into the test.

Choose the __Connect to Application__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Connect to Application step][1]

There are few notable properties of the step:

- __Process Name__ - defines the process to connect to; mandatory property.
- __Process Index__ - defines the index of the application process, if needed.
- __Set Focus__ - sets focus on the application one it is launched.
- __Auto Close__ - closes the application process when test completes.

![Connect to Application step properties][2]

[1]: /img/features/custom-steps/connect-to-app/step-builder-connec-app.png
[2]: /img/features/custom-steps/connect-to-app/extended-menu-connect-app.png

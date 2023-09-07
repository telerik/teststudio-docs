---
title: Change Window State
page_title: Change Window State
description: "How to change the Window state of the WPF application in Test Studio test run. Maximize/Minimize/Set application Window to normal during a test run in Test Studio"
position: 1
---
# Change Window State

The __Change Window State__ feature allows you to change the state of the WPF application window in test run-time. This article demonstrates how to add this type of step into the test.

Choose the __Change Window State__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Change Window State Step][1]

The __WindowState__ property of the step allows to change this to one of the following options:

- Normal
- Minimized
- Maximized
- Closed

The __WindowCaption__ property defines the window which state gets changed and is a mandatory field.

![Step Properties][2]

[1]: /img/features/custom-steps/change-window-state/step-builder-change-window.png
[2]: /img/features/custom-steps/change-window-state/extended-menu-change-window.png

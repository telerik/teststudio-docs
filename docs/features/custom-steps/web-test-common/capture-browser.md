---
title: Browser and Desktop Capture
page_title: Browser and Desktop Capture
description: "How to capture the browser window state/desktop state during a web test run with Test Studio. Test Studio captures a screenshot of the desktop during a web test run."
position: 6
---
# Browser and Desktop Capture

The __Capture Browser__ feature allows you to visually capture states at any point in a test and export them as PNG files to a specified folder. These images are larger and with higher quality than what is presented in the <a href="/features/test-maintenance/storyboard" target="_blank">Storyboard</a>.

This article demonstrates how to add this type of step into the test and use its properties.

- [Add Capture Browser Step](#add-capture-browser-step)
- [Capture Browser Step Properties](#capture-browser-step-properties)
- [Find the Images from Capture Browser Step](#find-the-images-from-capture-browser-step)

## Add Capture Browser Step

Choose the __Capture Browser__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Capture Browser step](/img/features/custom-steps/capture/fig0.png)

## Capture Browser Step Properties
![Add Capture Browser step][1]

Expand the __Capture__ step and toggle the __CaptureType__ to _Desktop_ or _Browser_ depending on what you need to capture. The __FileNamePrefix__ property lets you choose the file name for the images.

![Step Properties][2]

## Find the Images from Capture Browser Step

The images from __Capture Browser__ step are generated and stored when the test is <a href="/automated-tests/test-lists/test-list-execution" target="_blank">executed as part of a test list</a>.

> __Important!__
> <br>
> <br>
> Images from __Capture Browser__ step are not stored to disk when the test is executed through the <a href="/automated-tests/test-execution/quick-execution" target="_blank">Quick Execution mode</a>. The following message appears in the log:
> ` Image not captured to disk. CreateLogFile is set to 'false'.`

To store the Browser and Desktop Capture images to disk include the test in a test list and edit <a href="/features/test-lists/test-list-settings" target="_blank">its settings</a>. Ensure **CreateLogFile** is enabled and, optionally, specify the output directory for the image captures in the __LogLocation__ setting.

![Test List settings][3]

> In the VS plugin, the images are output to **ProjectsFolder\ProjectName\TestResults\User_MachineName_Date_Time\Out**

[1]: /img/features/custom-steps/capture/step-builder-browser-capture.png
[2]: /img/features/custom-steps/capture/extended-menu-browser-capture.png
[3]: /img/features/custom-steps/capture/fig3.png
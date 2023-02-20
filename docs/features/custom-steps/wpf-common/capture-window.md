---
title: Capture Window
page_title: Capture Window
description: "How to capture the application window state/desktop state during a WPF test run with Test Studio. Test Studio captures a screenshot of the desktop during a WPF test run."
position: 2
---
# Capture Application Window

The __Capture Window__ feature allows you to visually capture states at any point in a test and export them as PNG files to a specified folder. These images are larger and with higher quality than what is presented in the <a href="/features/test-maintenance/storyboard" target="_blank">Storyboard</a>.

This article demonstrates how to add this type of step into the test and use its properties.

- [Add Capture Window Step](#add-capture-window-step)
- [Capture Window Step Properties](#capture-window-step-properties)
- [Find the Images from Capture Window Step](#find-the-images-from-capture-window-step)

## Add Capture Window Step

Choose the __Capture Window__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Capture Window step](/img/features/custom-steps/capture/wpf-capture-step.png)

## Capture Window Step Properties

Expand the __Capture__ step and toggle the __CaptureType__ to _Desktop_ or _Window_ depending on what you need to capture. The __FileNamePrefix__ property lets you choose the file name for the images.

![Step Properties](/img/features/custom-steps/capture/wpf-capture-properties.png.png)

## Find the Images from Capture Window Step

The images from __Capture Window__ step are generated and stored when the test is <a href="/automated-tests/test-lists/test-list-execution" target="_blank">executed as part of a test list</a>.

> __Important!__
> <br>
> <br>
> Images from __Capture Window__ step are not stored to disk when the test is executed through the <a href="/automated-tests/test-execution/quick-execution" target="_blank">Quick Execution mode</a>. The following message appears in the log:
> ` Image not captured to disk. CreateLogFile is set to 'false'.`

To store the Window and Desktop Capture images to disk include the test in a test list and edit <a href="/features/test-lists/test-list-settings" target="_blank">its settings</a>. Ensure **CreateLogFile** is enabled and, optionally, specify the output directory for the image captures in the __LogLocation__ setting.

![Test List settings](/img/features/custom-steps/capture/fig3.png)

---
title: Storyboard
page_title: What is Storyboard
description: "Test Studio Storyboard is a visual representation of test steps. Test Studio automatically takes screenshots during recording"
position: 1
---
# Storyboard

Among other useful features, Test Studio takes screenshots of the current state of page during the test recording process and keeps these in a list called __Storyboard__. Where this is applicable, the step __target element is highlighted on the picture__. As this is a visual flow of how the test has progressed, it s a great time saver in helping others understand the state of the test at the time of recording, along with what the target elements of the tests were.

The below article describes the __Storyboard__ feature and how it can be helpful.

## Enable/Disable Storyboard Capture

By default capturing the __Storyboard is _enabled___ on project level and screenshot size is __set to a scale of 75%__. The __scale settings for captured images can be changed__ in the <a href="/features/project-settings/general" target="_blank">Project Settings -> General</a> tab. Uncheck the __Storyboard__ checkbox in the Project Settings if you need to __disable the Storyboard capture__.

## Where to Find the Storyboard?

The __Storyboard__ images are listed in a separate tab in the test pane.

![storyboard tab][1]

Once you switch to the __Storyboard__ tab, there is a vertical list of all steps in the test - select any to see the screenshot captured for it.

![List of steps][2]

## View Step Image Preview

Once a step from the list is selected, double-click it to open a separate __Image Preview__ window. In it you can zoom in and out of the screenshot using the _Magnifier_ icons, or the percentage dropdown. Pressing _Ctrl_ key on your keyboard and the mouse wheel will also zoom in and out.

![Image preview][3]

## Switch to Steps in Test

If you need to switch to the recorded steps in test and modify the currently reviewed one, you can __click on the step description__ in the Storyboard pane - Test Studio will switch automatically to the recorded steps and the current step will be selected.

![Switch to steps][4]

## Change Storyboard Orientation Layout

The list of all steps can be switched to horizontal - use the __Layout__ button to change where the list will be displayed.

![Switch to horizontal layout][5]

## Specific Images in Storyboard

Some of the steps recorded, or added, in a test do not interact with an element on page, or a screenshot is not applicable. In this case, the step is listed in the __Storyboard__ with a relevant __predefined image__. Examples for such steps are: _execution delays_, _test as step_, _coded steps_, _handling dialog steps_, etc.

![Predefined images for custom steps][6]

## Recapture Storyboard

While working on the tests in the automation project, you may need to __refresh the baseline of images__ recorded in the storyboard. To help you with this task, Test Studio provides the option to __recapture the storyboard__. Switch to the __Storyboard__ tab and hit the __Recapture__ button. This will trigger the test execution and let you choose the browser to use for this execution.

![Recapture][7]

Once a browser is selected, there is a prompt message to confirm the __Recapture__ attempt.

![warning][10]

## Export Storyboard as HTML

If you need to share the Storyboard images with anyone in your team, you can __export these to a HTML file__. Hit the **Export as HTML Documentation** button and choose a folder in which the exported file will be stored.

![Export][8]

Once the export is complete, you are prompted to choose whether you need to open the file. The HTML file gets opened in the default set browser on your machine and provides a report-like representation of the test, with test summary, step descriptions, and expandable images.

![Exported HTML][9]

[1]: /img/features/test-maintenance/storyboard/fig1.png
[2]: /img/features/test-maintenance/storyboard/fig2.png
[3]: /img/features/test-maintenance/storyboard/fig3.png
[4]: /img/features/test-maintenance/storyboard/fig4.png
[5]: /img/features/test-maintenance/storyboard/fig5.png
[6]: /img/features/test-maintenance/storyboard/fig6.png
[7]: /img/features/test-maintenance/storyboard/fig7.png
[8]: /img/features/test-maintenance/storyboard/fig8.png
[9]: /img/features/test-maintenance/storyboard/fig9.png
[10]: /img/features/test-maintenance/storyboard/fig10.png
[11]: /img/features/test-maintenance/storyboard/fig11.png

---
title: Browser and Desktop Capture
page_title: Browser and Desktop Capture
description: "How to capture the window state/dekstop state during a test run with Test Studio. Test Studio capture a screenshot of the desktop during a test run."
position: 8
---
# Browser and Desktop Capture

Capture full resolution images of the browser and desktop at designated steps in your test. These two steps allow you to visually capture states at any point in a test and export them as PNG files to a specified folder. These images will be larger and higher quality than what is presented in the <a href="/features/test-maintenance/storyboard" target="_blank">Storyboard</a> Test View. 

Highlight the Capture step and go the **Properties** area to change the file name for the images and toggle the Capture type between Browser and Desktop.

![Step Properties](/img/features/custom-steps/capture/fig1.png)

Once you add a Browser or Desktop Capture step to your test, and that test is part of a Test List, you can edit its settings.

> Images are not captured to disk when the Browser and Desktop steps are in a test that is ran with Quick Execution. The following message will show in the log:

> * *Image not captured to disk. CreateLogFile is set to 'false'.*

To capture the Browser and Desktop Capture images to disk, see the articles on creating and executing a Test List in the <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">Standalone version</a> or using the Test View in the <a href="/getting-started/test-execution/visual-studio-2012-and-later-test-list" target="_blank">Visual Studio plugin</a>.

![Step Properties](/img/features/custom-steps/capture/fig2.png)

Ensure **CreateLogFile** is checked. You can also specify the output directory for the image captures.

![Step Properties](/img/features/custom-steps/capture/fig3.png)

> In the VS plugin, the images are output to **ProjectsFolder\ProjectName\TestResults\User_MachineName_Date_Time\Out**
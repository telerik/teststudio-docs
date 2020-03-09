---
title: Element Images
page_title: Element Images | Test Studio Dev Documentation
description: "Settings to apply for the images recorded with the elements. Images used as backup search in Test Studio Dev." 
position: 3
---
# Element Images

Apply specific <a href="https://docs.telerik.com/teststudio/features/elements-explorer/elements-find-expression#elements-image" target="_blank">elements' image</a> settings related to locating elements on page on project level. The image recording is enabled by default, but you can choose whether to use these images during execution. To edit the images recorded for elements, you need to open the project in the <a href="https://www.telerik.com/teststudio" target="_blank">Standalone Test Studio product</a>.

![Element Images][1]

## Recording

Image recording for elements is enabled by default and the default threshold value set, to match the images, is 90. The usage of the desktop screenshot cache is also enabled by default. 

## Execution

- Enable/Disable the usage of recorded element images as backup search during test execution.

- Set the timeout for searching the image on page.

- Set the timeout to wait before starting the backup search by image.

- Enable/Disable scrolling of the page when searching an element by image.

## Image Preview

Displaying the image preview in the Elements Explorer is not available in the Test Studio Dev plugin for Visual Studio. If you need to <a href="https://docs.telerik.com/teststudio/features/elements-explorer/find-element-by-image" target="_blank">see and edit the images recorded for elements</a>, you need to open the project in the Standalone Test Studio product.

## Clear All Element Images

Deleting the elements' images is not available in the Test Studio Dev plugin for Visual Studio.

[1]: images/element-images/fig1.png

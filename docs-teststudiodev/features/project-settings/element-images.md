---
title: Element Images
page_title: Element Images | Test Studio Dev Documentation
description: "Settings to apply for the images recorded with the elements. Images used as backup search in Test Studio Dev." 
position: 3
---
# Element Images

Apply specific settings for <a href="https://docs.telerik.com/teststudio/features/elements-explorer/elements-find-expression#elements-image" target="_blank">elements' images</a> used for locating elements.

![Element Images][1]

## Recording

Image recording for elements in Test Studio Dev is enabled by default. The default image match threshold is 90 percent. Using the desktop screenshot cache is enabled by default.

> __Note__
> <br>
> <br>
> Changing the image recording settings and <a href="https://docs.telerik.com/teststudio/automated-tests/elements/find-element-by-image" target="_blank">editing the images</a> is only supported in Test Studio Standalone version.

## Execution

- Enable/Disable the usage of recorded element images as backup search during test execution.

- Set the timeout for searching the image on page.

- Set the timeout to wait before starting the backup search by image.

- Enable/Disable scrolling of the page when searching an element by image.

- Enable/Disable searching the elements by using their image first. The setting is used on project level and applies for every test step, unless it is otherwise specified in the <a href="/features/test-execution/test-list-settings" target="_blank">Test List Settings</a> or <a href="/features/test-maintenance/test-step-properties" target="_blank">Test Step Properties</a>.

## Image Preview

Displaying the image preview in Elements Explorer is not supported in Test Studio Dev. You can <a href="https://docs.telerik.com/teststudio/features/elements-explorer/find-element-by-image" target="_blank">see and edit the images recorded for elements</a> in the Standalone Test Studio product.

## Clear All Element Images

Deleting the elements' images is not not supported in Test Studio Dev.

[1]: images/element-images/fig1.png

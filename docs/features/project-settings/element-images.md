---
title: Element Images Settings
page_title: Element Images Settings
description: "Test Studio Project settings element images. Settings to apply for the images recorded with the elements. Images used as backup search in Test Studio"
position: 3
---
# Element Images

Apply specific <a href="/features/elements-explorer/elements-find-expression#elements-image" target="_blank">element's image</a> related settings on project level.

![Element Images][1]

## Recording

- Enable/Disable image recording for elements and set the default threshold value to match the images.

- Enable/Disable the usage of the desktop screenshot cache.

## Execution

- Enable/Disable the <a href="/features/elements-explorer/elements-find-expression#conditions-to-fall-back-to-find-elements-by-image" target="_blank">usage of recorded element images as backup search</a> during test execution.

- Set the timeout for searching the image on page.

- Set the timeout to wait before starting the backup search by image.

- Enable/Disable scrolling of the page when searching an element by image.

- Enable/Disable searching the elements by using their image first. The setting is used on project level and applies for every test step, unless it is otherwise specified in the <a href="/general-information/test-execution/test-list-settings" target="_blank">Test List Settings</a> or <a href="/features/test-maintenance/test-step-properties" target="_blank">Test Step Properties</a>.

## Image Preview

Enable/Disable displaying the image preview in the Elements Explorer.

## Clear All Element Images

This button allows you to delete the element images recorded for the whole project.

[1]: /img/features/project-settings/element-images/fig1.png

---
title: Element Images
page_title: Element Images Known Scenarios
description: "Element Images Known Scenarios Requiring Manual Adjustment"
position: 1
---
# Scenarios in Which Element Images Require Additional Adjustment

There are certain scenarios in which Test Studio will not record the correct image for an element, or not record an image at all. The known workflows are described in details below.

## Combobox and Textbox Element Image

Test Studio records the image for combobox and textbox incorrectly. The reason behind is that the image of the element gets recorded once the element is modified - text is entered, option is selected from the combobox. Thus, during execution the recorded image will not be available on the page before the step, which uses it, passes.

### Solution

To workaround this, you will need to [record the correct image manually](http://etsvetko:8080/teststudio/features/elements-explorer/find-element-by-image#recording-new-image).

## Image Capturing on Scaled Monitors

Currently the automatic capturing of images on displays with scaling settings different from 100%, will not record the correct element.

### Solution

To solution will be to [record the correct image manually](http://etsvetko:8080/teststudio/features/elements-explorer/find-element-by-image#recording-new-image).

## Recording WaitForExist Step

If the first recorded step against an element is *WaitForExists*, the recorded element will not contain any image. This is to avoid breaking some already existing user logic. 

### Solution

If it is necessary, the solution will be to [add the image manually](http://etsvetko:8080/teststudio/features/elements-explorer/find-element-by-image#recording-new-image).

## Recording Different Images for the Same Element

In some occasions Test Studio might record two very similar images for the same element. This is because the images are compared to be binary the same and in some situations, the browser renders the same element slightly different.

## Element with Multiple Images

In some scenarios the same element will have different image. For example if we work against a combo box and change its value from 1 to 2 to 3. Then the step that changes 1 to 2 will have different image compared to the step that changes 2 to 3. This is not a bug and we cannot provide a fix but it will be nice if we have this behavior documented.

[1]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig1.png
[2]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig2.png
[3]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig3.png

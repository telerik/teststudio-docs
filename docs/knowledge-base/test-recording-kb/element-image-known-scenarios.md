---
title: Element Images Known Scenarios
page_title: Element Images Known Scenarios
description: "Element Images Known Scenarios Requiring Manual Adjustment. Combobox element image is incorrect. textBox element image is incorrect. Element Image Capturing on Scaled Monitors. Recording WaitForExist Step element image is missing. Recording Different Images in different browsers for the Same Element. Using different images for a single element depending on the step where the same element is used. "
position: 1
---
# Scenarios in Which Element Images Require Additional Adjustment

There are certain scenarios in which Test Studio will not record the correct image for an element, or not record an image at all. The known workflows are described in details below.

## Recording WaitForExist Step

When recording a *WaitForExists* step, by default the recorded element will not contain any image. This is to avoid breaking some already existing user logic.

__Solution__

If it is necessary, the solution will be to [add the image manually](/features/elements-explorer/find-element-by-image#recording-new-image).

## Recording Different Images for the Same Element

In some occasions Test Studio might record two very similar images for the same element. This is because the images are compared to be binary the same and in some situations, the browser renders the same element slightly different.

## One Element with Multiple Images

In some scenarios the same element can have different image. For example, if we work against a combo box and change its value in two subsequent steps - from 1 to 2, then to 3. So, the step that changes 1 to 2 will have different image compared to the step that changes 2 to 3.

__Solution__

Test Studio allows you to capture manually a new image for an element and then apply it to the steps, which uses that element, separately. To cover the last listed scenario, you can follow these steps:

1. Open the target element to edit it and [switch to the Element Image settings](/features/elements-explorer/find-element-by-image).

2. [Record manually the new image](/features/elements-explorer/find-element-by-image#recording-new-image), which will be valid for the second step - the one, which changes the combo box value from 2 to 3 - you can choose any of the three available options (Upload new file, Select from browser, Run to step).

3. Once the desired image is correctly recorded, in the [Image Usage Details section](/features/elements-explorer/find-element-by-image#image-usage-details) choose the step to apply it to from the **"Used By"** dropdown and then click on the **Apply** button.

4. Save the changes. Switching the steps, which uses the element, from the same **"Used By"** dropdown, will display the different images accordingly.

[1]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig1.png
[2]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig2.png
[3]: /img/knowledge-base/test-recording-kb/kendoui-duplicate-elements/fig3.png

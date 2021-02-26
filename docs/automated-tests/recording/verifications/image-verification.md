---
title: Image Verification
page_title: Image Verification
description: "Test Studio Image verification. Verify an image in Test Studio test run. Verify image across browsers and machines."
position: 4
---
# Image Verification

You can build an image verification against specific elements for pixel-by-pixel visual verifications in tests. The image verification feature is based on an element’s visual rendering rather than the properties or attributes of that element. An application with rich graphic rendering can leverage this functionality to automate some of its test scenarios that have always needed manual visual inspection to verify. The image verification in Test Studio allows you to refine your verification area down to the pixel level within an element and also assign a threshold for the matching.

## Best practices

There are few things that could ensure more stable and reliable test execution:

&nbsp; &nbsp; ![Green][1] Use Image Verification when you need to verify an exact and static image, such as a logo, button, or icon. 

&nbsp; &nbsp; ![Red][2] Do not use Image Verification to verify a specific color, an image with text content, or a dynamic slide show.

## How to record an image verification step

1.&nbsp; Create a Web Test and click Record.

2.&nbsp; Navigate to the application under test, for example www.Telerik.com.

3.&nbsp; Enable highlighting from the Recorder.

![Enable Highlighting][3]

4.&nbsp; Hover over the image, for example the Progress Telerik logo in the header, and select **Build Step...** from the context menu.

![Build Step][4]

5.&nbsp; In the Recorder click **Verifications > Image**.

![Image][5]

By default, **Verify Entire Image** is checked and the **Threshold** is set to 90%.

> We recommend keeping the Threshold around 90%. A setting of 100% equals an exact match and the verification will fail, if it is off by a single pixel.

6.&nbsp; Uncheck **Verify Entire Image** to refine the comparison area. Either enter coordinates or drag the desired selection area within the image.

![Refine][6]

7.&nbsp; Click **Add Step** and notice the Verify image step is added to the test.

![Step Added][7]

## Configure the recorded image verification step

You can configure the threshold and scrolling options that will be used during test execution.

![Configure Test Step Options][8]

After the image verification step is recorded, you can make changes to the captured image and even recapture it. To do that, you need to select the image verification step and click on the image. This image will be associated with the test step, but all features and options for <a href="/features/elements-explorer/find-element-by-image#image-usage-details" target="_blank">modifying element image</a> are available. Only the **Image Recognition Settings** are not available, because the threshold is a test step option.

![Recapture Image][9]

## Troubleshooting

If you receive a failure on an Image Verification step, you can explore the <a href="/general-information/test-results/step-failure-details" target="_blank">step failure details</a> for more details. In addition to the failure details, you can analyze the expected and actual image under the **Images** tab.

![Failure Details][10]

[1]: /img/features/recorder/verifications/image-verification/fig1.png
[2]: /img/features/recorder/verifications/image-verification/fig2.png
[3]: /img/features/recorder/verifications/image-verification/fig3.png
[4]: /img/features/recorder/verifications/image-verification/fig4.png
[5]: /img/features/recorder/verifications/image-verification/fig5.png
[6]: /img/features/recorder/verifications/image-verification/fig6.png
[7]: /img/features/recorder/verifications/image-verification/fig7.png
[8]: /img/features/recorder/verifications/image-verification/fig8.png
[9]: /img/features/recorder/verifications/image-verification/gif9.gif
[10]: /img/features/recorder/verifications/image-verification/fig10.png

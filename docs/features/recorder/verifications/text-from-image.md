---
title: Text from Image Verification
page_title: Text from Image Verification
description: "Test Studio Text from Image Verification. OCR text verification. Verify text from an image in Test Studio test run."
position: 5
---
# Text from Image Verification

You can verify specific text from an image in your application. Test Studio will read the full or part of the text from the image and allow you to verify the content. You can also extract this text and use it as a variable in other test steps in your test. This feature unlocks new possibilities to automate the images in your applications.

## Best practices

There are few things that could ensure more stable and reliable test execution:

&nbsp; &nbsp; ![Green][1] Use Text from Image Verification when you need to verify the text in an exact and static image.

&nbsp; &nbsp; ![Green][1] Specify only the part of the image which has the text, because logos and other symbols might be misinterpreted as characters.

&nbsp; &nbsp; ![Red][2] Do not use Text from Image Verification to verify a dynamic slide show or GIFs.

## How to record a text from image step

1.&nbsp; Create a Web Test and click Record.

2.&nbsp; Navigate to the application under test, for example "www.telerik.com".

3.&nbsp; Enable highlighting from the Recorder.

![Enable Highlighting][3]

4.&nbsp; Hover over the image, for example the Forbes logo, and add a verification, wait or <a href="/features/recorder/verifications/extraction" target="_blank">extract step</a> from the context menu.

![Build Quick Step][4]

5.&nbsp; Another way to add a Text from Image step is to select **Build Step...** from the context menu. 

![Build Step][5]

6.&nbsp; In the Recorder click **Verifications > TextFromImage**. 

![Image][6]

7.&nbsp; By default, **OCR Entire Image** is checked. Uncheck this option to refine the comparison area and the image text.

![Refine][7]

8.&nbsp; Click **Add Step** and notice the Verify text steps are added to the test.

![Step Added][8]

## Configure the recorded text from image step

You can configure the TextToMatch and CompareType that will be used during test execution. That said, if you need to change the image, you need to record the verification step again.

![Configure Test Step][9]

## Troubleshooting

If you receive a failure on the verification step, you can explore the <a href="/general-information/test-results/step-failure-details" target="_blank">step failure details</a> for more details. In addition to the failure details, you can analyze the expected and actual image under the **Images** tab.

![Failure Details][10]

[1]: /img/features/recorder/verifications/text-from-image/fig1.png
[2]: /img/features/recorder/verifications/text-from-image/fig2.png
[3]: /img/features/recorder/verifications/text-from-image/fig3.png
[4]: /img/features/recorder/verifications/text-from-image/fig4.png
[5]: /img/features/recorder/verifications/text-from-image/fig5.png
[6]: /img/features/recorder/verifications/text-from-image/fig6.png
[7]: /img/features/recorder/verifications/text-from-image/fig7.png
[8]: /img/features/recorder/verifications/text-from-image/fig8.png
[9]: /img/features/recorder/verifications/text-from-image/fig9.png
[10]: /img/features/recorder/verifications/text-from-image/fig10.png

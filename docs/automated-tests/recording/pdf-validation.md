---
title: Validate PDF File
page_title: How to Validate PDF File
description: "Test Studio test Recording supports codeless PDF validation codeless. validate the content of a PDF file in Test Studio test. Add codeless verifications for the text or images in PDF file in Test Studio tests. Compare two PDF files in Test Studio test. "
position: 3
---
# Validate PDF File

PDF files are commonly used for generating reports and documents across different business areas and companies. Test Studio provides the functionality to validate the content of PDF file out-of-the-box and completely codeless.

Find out how to open a PDF file in the browser and record the scenario actions in a Test Studio test.

## Download and Open PDF File

Usually when working with PDF exports, you need to generate and download the PDF file, then open it and validate its content. And this is a complete end-to-end scenario in a Test Studio recording session. Whenever a __PDF file is downloaded__, the recording process detects it and __opens it in a new tab of the recording browser__. As a result there is a sequence of steps recorded - click the download button, handle the download dialog, open the downloaded PDF, connect to the tab with PDF file opened.

![Steps recorded automatically when pdf is downloaded][1]

## Open Local PDF File

Another scenario to validate PDF file is to open an existing locally stored file and validate its content. To accomplish this in a Test Studio test, you can use the <a href="/features/custom-steps/open-pdf" target="_blank">__Open PDF File__ step</a> from the Step Builder. Insert a valid path to an existing PDF file to open it during the test.

![Add Open pdf step in test from step builder][2]

> **Tip**
> <br>
> <br>
> If you have added the __Open PDF__ step without active recording session and you need to __record the verification step for its content__, you can <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">execute the test partially</a> to the step, which opens the PDF. This will open the PDF file in the browser with attached recorder to it and you can continue recording the scenario.

## Control What Is Visible from the PDF File

When a PDF file is opened in active recording session, the toolbar to control the PDF visible part is rendered in the page and Test Studio recorder has free access to it.

![pdf control toolbar][3]

This means you can add steps to zoom in/out, change the displayed page of the document, set the zoom level from the dropdown, verify the value of the current set zoom level, etc.

![steps recorded against the pdf control toolbar][4]

> **Tip**
> <br>
> <br>
> If you are using a __multiple page PDF document, ensure that the correct page is displayed__ before validating its content - you can go to exact page using the _Page_ input field.

## Record Steps Against the PDF File

When the PDF is opened in the browser, you can __add any verification steps__, which Test Studio provides:

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick Verification</a>/ <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">Wait Steps</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced Verification</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extract Text</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">Extract Text from Image</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Verify Image</a>

## Compare PDF Files

Comparing two PDF files is not a straight forward scenario, but combining the Test Studio features allows you to accomplish even such difficult task. Here are the steps for example scenario:

1. Navigate to the tested page.
1. Generate and download the PDF file.
1. Once opened, validate its title and date of creation, for example. (Let's use a report as baseline for the example)
1. Store these values in extracted variables using the <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extraction step</a>.
1. Close the PDF.
1. <a href="/features/custom-steps/open-pdf" target="_blank">Add a step</a> to open the other already existing PDF report.
1. Add the verification steps to validate its title and the date of creation.
1. Close the PDF.
1. Data drive these verification steps using the extracted variables from the downloaded file. 
1. Execute the test and it will use the values extracted from the downloaded file to verify if this is the same with the content of the existing PDF file.

## See also ##


[1]: /img/automated-tests/recording/validate-pdf/fig1.png
[2]: /img/automated-tests/recording/validate-pdf/fig2.png
[3]: /img/automated-tests/recording/validate-pdf/fig3.png
[4]: /img/automated-tests/recording/validate-pdf/fig4.png
[5]: /img/automated-tests/recording/validate-pdf/fig5.png
[5a]: /img/automated-tests/recording/validate-pdf/fig5a.png
[6]: /img/automated-tests/recording/validate-pdf/fig6.png
[10]: /img/automated-tests/recording/validate-pdf/fig10.png
[11]: /img/automated-tests/recording/validate-pdf/fig11.png
[12]: /img/automated-tests/recording/validate-pdf/fig12.png


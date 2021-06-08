---
title: Automate PDF Validation
page_title: How to Validate PDF File in Test Studio
description: "Test Studio supports codeless PDF validation during test recording and allows you to validate the content of a PDF file."
position: 3
---
# Validate PDF File

PDF files are commonly used for generating reports and documents. Test Studio provides codeless, out-of-the-box automation for PDF validation.

This article describes how to open a PDF file in the browser and record the actions from the test scenario.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Download and Open PDF File

The usual procedure when you export data to PDF includes the following actions:

1. Generate the file's content.
1. Download the content as a PDF file.
1. Open the PDF file to validate if the expected information is available in the generated file.

Test Studio allows you to create a test automation scenario for these actions. To create the automation scenario, start by downloading a PDF file and Test Studio will do the rest:

1. The recording process in Test Studio detects that you download a PDF file.

1. Test Studio opens the file in a new browser tab.

1. Test Studio records the following sequence of steps in the test:

   * Click the download button.
   * Handle the 'Download' dialog.
   * Open the downloaded PDF file.
   * Connect to the browser tab with the opened PDF file.
   * Record several steps that check the file's content and automate the PDF validation.

![Steps recorded automatically for test automation pdf][1]

## Open Local PDF File

Another scenario for PDF test automation is to open a locally stored file and validate its content. To accomplish this in a Test Studio test, you use the <a href="/features/custom-steps/open-pdf" target="_blank">Open PDF</a> step in the **STEP BUILDER**. Insert a valid path to an existing PDF file to open it during the test execution.

![Add Open pdf step in test from step builder][2]

To open the listed PDF file in the browser and continue recording, use the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">__Open PDF__</a> context menu option for the desired test step. Choose the browser to use, and continue the recording session.

![Open pdf from step context menu in test from step builder][2a]

Once the PDF file is opened in the selected browser recording session, the Test Studio recorder captures a __Connect to pop-up window__ step for the PDF file in the test, and you can continue recording.

![Open pdf from step context menu in test from step builder][2b]

> **Tip**
> <br>
> <br>
> If you have added the __Open PDF__ step without an active recording session, you can also record the next steps by using the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank"> partial execution options for the test</a>.

## Control What Is Visible from the PDF File

When a PDF file is opened in an active recording session, the toolbar that controls the visible PDF area is rendered on the page, and the Test Studio recorder has free access to it.

![pdf control toolbar][3]

This means that you can add steps to zoom in or out, change the displayed page of the document, set the zoom level from the dropdown, verify the value of the current zoom level, etc.

![steps recorded against the pdf control toolbar][4]

> **Tip**
> <br>
> <br>
> If you are using a PDF document with multiple pages, ensure that the correct page is displayed before validating its content - you can go to the desired page by using the _Page_ input field.

## Record Steps Against the PDF File

As a PDF validation automation tool, Test Studio allows you to add different verification steps, which help in validating the content of the file and, optionally, reuse it later in the test automation actions.

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick Verification</a>/ <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">Wait Steps</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced Verification</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extract Text</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">Extract Text from Image</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Verify Image</a>

## Compare PDF Files

Comparing the content of two PDF files is not a straight-forward scenario, but combining Test Studio features allows you to automate even such difficult tasks. Here are the steps for a sample scenario that compares PDF files:

1. Navigate to the tested page.
1. Generate and download the PDF file.
1. Once opened, validate its title and date of creation, for example.
1. Store these values in extracted variables by using the <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extraction step</a>.
1. Close the PDF.
1. <a href="/features/custom-steps/open-pdf" target="_blank">Add a step</a> to open the other already existing PDF file.
1. Add the verification steps to validate its title and the date of creation.
1. Close the PDF.
1. Data-drive these verification steps by using the extracted variables from the downloaded file.
1. Execute the test and it will use the values extracted from the downloaded file to verify if the content in both files is identical.

## See also ##

* 

[1]: /img/automated-tests/recording/validate-pdf/fig1.png
[2]: /img/automated-tests/recording/validate-pdf/fig2.png
[2a]: /img/automated-tests/recording/validate-pdf/fig2a.png
[2b]: /img/automated-tests/recording/validate-pdf/fig2b.png
[3]: /img/automated-tests/recording/validate-pdf/fig3.png
[4]: /img/automated-tests/recording/validate-pdf/fig4.png
[5]: /img/automated-tests/recording/validate-pdf/fig5.png
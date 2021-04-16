---
title: Automate PDF Validation
page_title: How to Validate PDF File in Test Studio
description: "Test Studio test Recording supports codeless PDF validation codeless. Test automation pdf with Test Studio. validate the content of a PDF file in Test Studio test. Test Studio is among the pdf automation tools. Validate PDF content through codeless verifications for the text or images in PDF file in Test Studio tests. Compare two PDF files in Test Studio test. Open a PDF file in Test Studio test and read its content. During the test run there is a PDF file created and stored locally on the hard disc. I would like to open that one and read its content."
position: 3
---
# Validate PDF File

PDF files are commonly used for generating reports and documents across different business areas and companies. Test Studio, as being among the PDF automation tools, provides the functionality for __PDF validation automation__ out-of-the-box and completely codeless.

Find out how to open a PDF file in the browser and record the scenario actions in a Test Studio test.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Download and Open PDF File

Usually when working with data exported to PDF file, you need to generate the specific content and download the PDF file, then open it and validate if the expected information is listed in the generated file.

And this is a complete end-to-end scenario for test automation of a PDF file in a Test Studio recording session. Whenever a __PDF file is downloaded__, the recording process detects it and __opens it in a new tab of the recording browser__. As a result, there is a sequence of steps recorded - click the download button, handle the download dialog, open the downloaded PDF, connect to the tab with PDF file opened, record different type of steps to check the content and automate the PDF validation.

![Steps recorded automatically for test automation pdf][1]

## Open Local PDF File

Another scenario for PDF test automation is to __open an existing locally stored file__ and validate its content. To accomplish this in a Test Studio test, you can use the <a href="/features/custom-steps/open-pdf" target="_blank">__Open PDF File__ step</a> from the Step Builder. Insert a valid path to an existing PDF file to open it during the test execution.

![Add Open pdf step in test from step builder][2]

To open the listed PDF file in the browser and __continue recording__, choose the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> option __'Open PDF'__. Choose the browser to use and continue the recording session.

![Open pdf from step context menu in test from step builder][2a]

> **Note**
>
> Open PDF step is not supported in Internet Explorer.

Once the PDF file is opened in the selected browser recording session, Test Studio recorder captures a __Connect to popup window__ step with the localhost address for the PDF file in the test and you can continue recording.

![Open pdf from step context menu in test from step builder][2b]

> **Tip**
> <br>
> <br>
> If you have added the __Open PDF__ step without active recording session you can also __record the next steps__ using the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank"> partial execution options for the test</a>.

## Control What Is Visible from the PDF File

When a PDF file is opened in active recording session, the __toolbar to control the PDF visible part is rendered in the page__ and Test Studio recorder has free access to it.

![pdf control toolbar][3]

This means you can __add steps to zoom in/out, change the displayed page of the document, set the zoom level from the dropdown, verify the value of the current set zoom level__, etc.

![steps recorded against the pdf control toolbar][4]

> **Tip**
> <br>
> <br>
> If you are using a __multiple page PDF document, ensure that the correct page is displayed__ before validating its content - you can go to exact page using the _Page_ input field.

## Record Steps Against the PDF File

As a PDF validation automation tool Test Studio allows you to add different __verification steps__, which will help in validating the content of the file and, optionally, reuse it later in the test automation actions.

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick Verification</a>/ <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">Wait Steps</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced Verification</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extract Text</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">Extract Text from Image</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Verify Image</a>

## Compare PDF Files

Comparing the content of two PDF files is not a straight-forward scenario, but combining the Test Studio features allows you to automate even such difficult task. Here are the steps for example scenario:

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

* 

[1]: /img/automated-tests/recording/validate-pdf/fig1.png
[2]: /img/automated-tests/recording/validate-pdf/fig2.png
[2a]: /img/automated-tests/recording/validate-pdf/fig2a.png
[2b]: /img/automated-tests/recording/validate-pdf/fig2b.png
[3]: /img/automated-tests/recording/validate-pdf/fig3.png
[4]: /img/automated-tests/recording/validate-pdf/fig4.png
[5]: /img/automated-tests/recording/validate-pdf/fig5.png
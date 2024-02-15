---
title: Open PDF
page_title: Open DPF File
description: "How to open a locally stored PDF in Test Studio web test and validate its content" 
position: 2
---
# Open PDF File Step

The __Open PDF File__ step allows you to <a href="/automated-tests/recording/pdf-validation#open-local-pdf-file" target="_blank">open an existing PDF file</a> stored locally on your disk, load it in the browser and validate its content.

This article demonstrates how to add this type of step into the test.

Choose the __Open PDF File__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Open PDF][1]

The __PdfFilePath__ property of the step specifies the file to open and accepts full qualified file path.

![Path to PDF][2]

> **Note**
>
> Open PDF step is __not supported__ in Internet Explorer.

[1]: /img/features/custom-steps/open-pdf/step-builder-open-pdf.png
[2]: /img/features/custom-steps/open-pdf/pdf-dropdown.png
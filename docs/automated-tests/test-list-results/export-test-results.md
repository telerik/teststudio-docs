---
title: Maintain Test List Results
page_title: Maintain Test List Results
description: "Test Studio test list results export. Can I export the test list results of a test list execution in Test Studio. "
previous_url: /user-guide/test-results/export-test-results.aspx, /user-guide/test-results/export-test-results, /getting-started/test-results/export-test-results
position: 2
---
# Maintain Test List Results

The results generated from a test list execution are stored on project level and populated in the __Results__ tab in the Test Studio project.

The tools ribbon in the __Results__ tab allows you to manage these results - delete all of them, or only the selected, export the results in different file formats, including send these as an email attachment, submit a bug, manage the scheduled test lists results (for the occasion when scheduling the tests in the Test Studio Scheduling configuraion).

In this article you can find details for the following topics:

- __Delete Results__
- __Options Specific for Scheduled Results__
- __Export Results__
- __Send Results as Email Attachment__
- __Submit Bug from Failed Test Result__

> __Note__
><br>
><br>
> The results from __local test list runs are stored in the project root folder__ under the sub-folder named _Results_. All these can be maintained in a File Explorer - however, __any changes applied outside of Test Studio, may affect the file structure and corrupt__ it. That way a result file may no longer be displayed in the project's calendar view.

## Delete Results

Select a results entry from the calendar in the Test Studio _Results_ tab. To delete it, you can use the __X_ button__, which appears for each result entry when hovered with the mouse, or the __Delete Selected__ button in the tools ribbon. This button can be used for deleting multiple selected results. __Delete All___ button will delete all results generated in the project so far.

Each _Delete_ action will prompt a message to confirm the delete action for the selected result.

![Delete Results][10]

> __Tip__
><br>
><br>
> You can select multiple results using the *Shift* key or *Ctrl* key + click.

## Options Specific for Scheduled Results

The _Reload_, _Publish to Server_ and _Manage Results_ buttons are specific for scheduled test list results and are active in a configured Scheduling setup.

## Export Results

The format of the Test Studio results file is specific and is only readable in Test Studio. The file extension for the results files is __*.aiiresult__ and can be only opened on a machine with Test Studio installed. To overcome this limitation Test Studio provides the built-in option to export the results in different formats.

* **HTML**: Export Test Studio run result to an HTML document.

* **Xml**: Export Test Studio run result to an Xml document.

* **Word**: Export Test Studio run result to a Microsoft Word document.

* **Excel**: Export Test Studio run result to a Microsoft Excel document.

* **VS Result File**: Export Test Studio run result to Visual Studio test result (*.trx file).

## Export Automated Test List Results

Select a results entry and double click it to display its details on the right side of the _Calendar_ view. All options for exporting the results file into a different format are now active to use.

![Export Options][11]

Choose the most appropriate file format and click the corresponding button. A _Save As_ dialog appears and lets you choose the file name and folder location to store the exported results file.

## Multiple Results Export

_HTML_ and _Xml_ export supports multiple results selection. Multiple results can be selected by using the *Shift* key or *Ctrl* key + click.

![Export HTML][6]

> __Note__
><br>
><br>
> Exporting results to ___HTML_ and _Xml_ requires a default program to be set for these type of files__ as the exported file is automatically opened.

## Email Test List Results

All of the supported export file types can be directly sent via email. Select a test list result entry and use the __Email__ button dropdown to generate an email with the exported file attached.

> **Note**
><br>
><br>
> Once the email is generated the _From_ field in Outlook email shows a default and not valid Telerik email address - __change this to the configured email client__ by selecting it in the email's _From_ button dropdown.

![Email Single results][7]

> __Tip__
><br>
><br>
> Emailing _HTML_ and _Xml_ run results supports __multiple test results selection__.

![Email multiple HTML/Xml][8]

> **Note**
><br>
><br>
> To generate an email with _Word_ or _Excel_ file attached, the selected test list result details need to be opened. To drill down the details, __double click the results entry__.

## Export Performance Test List Results

1.&nbsp; Execute a <a href="/getting-started/test-execution/test-lists-type-standalone" target="_blank">Performance Test List</a>.

2.&nbsp; Click the **stopwatch** icon in the **Test Results** panel:

![Stopwatch icon][3]

3.&nbsp; Click an export format from the **Export** ribbon to export the results.

![Performance export table][4]

>**Note:** When opening an exported Excel result you receive the following warning:

*The file you are trying to open, 'fileName.xls', is in a different format than specified by the file extension. Verify that the file is not corrupted and is from a trusted source before opening this file. Do you want to open the file now?*

![Excel warning][5]

When Test Studio exports data to Excel format it actually exports it as an HTML structure (which Excel can successfully parse). The alert is a new security feature in Excel 2007 called Extension Hardening, which ensures that the file content being opened matches the extension type specified in the shell command that is attempting to open the file. The file must be in XLS (BIFF8) or XLSX (Open XML) file format to open without this warning prompt. If the file type is a different format (such as HTML, XML, CSV, etc.) the prompt is expected since the file content is different that the extension or MIME type.

Click **Yes** to proceed safely.

* **TFS Build Server**: Publish the currently selected run result to the build server to be associated with a specific product build.

* **Submit Bug**: Load the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and log a bug about the failed result in your previously configured bug tracking application.


[1]: /img/general-information/test-results/export-test-results/fig1.png
[2]: /img/general-information/test-results/export-test-results/fig2.png
[3]: /img/general-information/test-results/export-test-results/fig3.png
[4]: /img/general-information/test-results/export-test-results/fig4.png
[5]: /img/general-information/test-results/export-test-results/fig5.png
[6]: /img/general-information/test-results/export-test-results/fig6.png
[7]: /img/general-information/test-results/export-test-results/fig7.png
[8]: /img/general-information/test-results/export-test-results/fig8.png
[10]: /img/automated-tests/test-list-results/maintain-results/fig10.png
[11]: /img/automated-tests/test-list-results/maintain-results/fig11.png

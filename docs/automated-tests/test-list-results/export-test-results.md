---
title: Maintain Test List Results
page_title: Maintain Test List Results
description: "Test Studio test list results export. Can I export the test list results of a test list execution in Test Studio. "
previous_url: /user-guide/test-results/export-test-results.aspx, /user-guide/test-results/export-test-results, /getting-started/test-results/export-test-results
position: 2
---
# Maintain Test List Results

The results generated from test list executions are stored on project level and populated in the __Results__ tab in the Test Studio project.

The tools ribbon in the __Results__ tab allows you to manage these results - delete all of them, or only the selected, export the results in different file formats, including send these as an email attachment, submit a bug, manage the scheduled test lists results (for test list runs initiated through the <a href="/automated-tests/scheduling/remote-scheduled-run" target="_blank">Test Studio Scheduling configuration</a>).

In this article you can find details for the following topics:

- [__Delete Results__](#delete-results)
- [__Options Specific for Scheduled Results__](#options-specific-for-scheduled-results)
- [__Export Results__](#export-results)
- [__Send Results as Email Attachment__](#email-test-list-results)
- [__Submit Bug from Failed Test Result__](#submit-bug-from-failed-test-result)

> __Note__
><br>
><br>
> The results from __local test list runs are stored in the project root folder__ under the sub-folder named _Results_. All these can be maintained in a File Explorer - however, __any changes applied outside of Test Studio, may affect the file structure and corrupt__ it. That way a result file may no longer be displayed in the project's calendar view.

## Delete Results

Select a results entry from the calendar in the Test Studio _Results_ tab. To delete it, you can use the ___X_ button__, which appears for each result entry when hovered with the mouse, or the __Delete Selected__ button in the tools ribbon. This button can be used for deleting multiple selected results. __Delete All__ button will delete all results generated in the project so far.

Each _Delete_ action will prompt a message to confirm the delete action for the selected result.

![Delete Results][10]

> __Tip__
><br>
><br>
> You can select multiple consecutive results using clicks + the *Shift* key, or any multiple results using the *Ctrl* key + clicks.

## Reload the Results View

The __Reload__ button allows you to reload the listed results in the calendar. The _Results_ tab view gets refreshed each time when the focus is switched to it. But in the cases when a test list run was initiated and you need to check the result once this is finished, you can use the __Reload__ button for this. You can have in mind that although the test runs seem to be finished, there is always a short delay until the result can be populated in the _calendar_ view.

![Reload Results][12]

## Options Specific for Scheduled Results

The __Publish to Server__ and __Manage Results__ buttons are specific for scheduled test list results and are active in a <a href="/automated-tests/scheduling/remote-scheduled-run" target="_blank">configured Scheduling setup</a> and test lists executed through this configuration.

- __Publish to Server__ - use this button, if you need to upload the result of a local test list run to the Storage database.
- __Manage Results__ - this button displays a dialog with list of all test list runs initiated through the Scheduling service (including _Run remotely_ and _Scheduled test lists_). You can review these runs with details for start and end time and containing project. Deleting an entry from this list will result in deleting the result file for the selected run. 

![Publish/Manage Results to Storage][13]

## __Export Results__

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

_HTML_ and _Xml_ export supports multiple results selection. __Multiple results can be selected by using the *Shift* key or *Ctrl* key + click__.

![Export HTML][6]

> __Note__
><br>
><br>
> Exporting results to ___HTML_ and _Xml_ requires a default program to be set for these type of files__ as the exported file is automatically opened.

### Export Performance Test List Results

When you drill down the results of a <a href="/getting-started/test-execution/test-lists-type-standalone" target="_blank">Performance Test List</a> execution, there is an additional icon listed in the **Test Results** panel - this is the **Stopwatch**.

![Stopwatch icon][3]

Hitting the **Stopwatch** button will switch the result to present the overview of the performance test execution (similar to what details can be explored in the <a href="/automated-tests/performance/overview-button" target="_blank">Overview view</a> in the __Performance tab__). These performance results can be exported to Word and Excel trough the corresponding buttons.

> **Note**
><br>
><br>
> When opening an exported Excel result you receive the following warning:
> ``` The file you are trying to open, 'fileName.xls', is in a different format than specified by the file extension. Verify that the file is not corrupted and is from a trusted source before opening this file. Do you want to open the file now? ```
><br>
><br>
> This is because of the mechanism, which Test Studio uses to export the data, and some security features of Excel.
><br>
>You can click on __Yes__ to confirm the message and proceed safely.

## Email Test List Results

All of the supported export file types can be directly __sent via email__. Select a test list result entry and use the ___Email_ button dropdown__ to generate an email with the exported file attached.

> **Note**
><br>
><br>
> Once the email is generated the _From_ field in Outlook email shows a default and not valid Telerik email address - __change this to the configured email client on the machine__ by selecting it in the email's _From_ button dropdown.
><br>
> If you send the email without changing the default set Telerik email, you will get an email message from __System Administrator__ with title __Undelivarable__. Generate the email again and ensure to set your email address, from which to send the message. 

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

## Submit Bug from Failed Test Result

* **TFS Build Server**: Publish the currently selected run result to the build server to be associated with a specific product build.

* **Submit Bug**: Load the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and log a bug about the failed result in your previously configured bug tracking application.


[1]: /img/automated-tests/test-list-results/export-test-results/fig1.png
[2]: /img/automated-tests/test-list-results/export-test-results/fig2.png
[3]: /img/automated-tests/test-list-results/export-test-results/fig3.png
[4]: /img/automated-tests/test-list-results/export-test-results/fig4.png
[5]: /img/automated-tests/test-list-results/export-test-results/fig5.png
[6]: /img/automated-tests/test-list-results/export-test-results/fig6.png
[7]: /img/automated-tests/test-list-results/export-test-results/fig7.png
[8]: /img/automated-tests/test-list-results/export-test-results/fig8.png
[10]: /img/automated-tests/test-list-results/export-test-results/fig10.png
[11]: /img/automated-tests/test-list-results/export-test-results/fig11.png
[12]: /img/automated-tests/test-list-results/export-test-results/fig12.png
[13]: /img/automated-tests/test-list-results/export-test-results/fig13.png
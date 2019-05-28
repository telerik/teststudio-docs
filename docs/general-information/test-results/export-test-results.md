---
title: Export Test Results
page_title: Export Test Results
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-results/export-test-results.aspx, /user-guide/test-results/export-test-results, /getting-started/export-test-results
position: 1
---
# Export Test Results

The **Export** ribbon allows you to create HTML, Xml, Word, Excel, VS Result File and TFS Build Server versions of a test list results. If you have access to Team Foundation Server (TFS), you can  reload results from and publish to the server using the buttons in the **Scheduling Server** ribbon. For more details see the <a href="/features/scheduling-test-runs/Overview" target="_blank">Test Scheduling</a> article series.

![Results tab][1]

* **HTML**: Export run result to an HTML document.

* **Xml**: Export run result to an Xml document.

* **Word**: Export run result to a Microsoft Word document.

* **Excel**: Export run result to a Microsoft Excel document.

* **VS Result File**: Export run result to Visual Studio test result .trx file.

* **TFS Build Server**: Publish the currently selected run result to the build server to be associated with a specific product build.

* **Submit Bug**: Load the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and log a bug about the failed result in your previously configured bug tracking application.

## Export Automated Test List Results

1.&nbsp; Execute a standard automated test list.

2.&nbsp; Double click the result in the <a href="calendar" target="_blank">Calendar</a> to drill down into it to be able to export to Word and Excel format. HTML and Xml export is  available from any level of the Calendar view. 

3.&nbsp; Perform the export.

![Export table][2]

## Multiple Results Export

HTML and Xml export supports multiple run results export. Please note that HTML and Xml export requires there is a default program set since the exported file is automatically opened. 

1.&nbsp; Execute a standard automated test list few times. 

2.&nbsp;  Select multiple test list results from the Calendar view using Shift and/or Ctrl keys. 

3.&nbsp;  Perform the export.

![Export HTML][6]

## Email Test List Results

Additionally any results within the calendar view could be emailed using the default email client configured on the host machine. **To email Word and Excel exports the test results should be drilled down.** 

![Email Word/Excel][7]

**HTML and Xml emailing supports multiple test results emailing.**

![Email HTML/Xml][8]

>**Note:** Once the email is generated the From field in Outlook email shows a default Telerik email address which needs to be changed to the configured one on the host machine.  

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

[1]: /img/getting-started/test-results/export-test-results/fig1.png
[2]: /img/getting-started/test-results/export-test-results/fig2.png
[3]: /img/getting-started/test-results/export-test-results/fig3.png
[4]: /img/getting-started/test-results/export-test-results/fig4.png
[5]: /img/getting-started/test-results/export-test-results/fig5.png
[6]: /img/getting-started/test-results/export-test-results/fig6.png
[7]: /img/getting-started/test-results/export-test-results/fig7.png
[8]: /img/getting-started/test-results/export-test-results/fig8.png

---
title: Dialogs
page_title: Dialogs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/dialogs-and-popups/dialogs.aspx, /user-guide/dialogs-and-popups/dialogs
position: 1
---
# Dialogs


- Not all test steps play out directly inside the browser. Web pages can display popup dialog windows in the form of alerts, confirmations, and other browser instances. 
- Test Studio allows you to track and respond to dialog windows and can handle HTML popups and Win32 dialogs.
- An HTML popup is a new browser window that is detected automatically. Test Studio will prompt you to automate the popup.
- A Win32 dialog is not a browser window, but a dialog displayed by the Windows operating system.
- Test Studio typically inserts the appropriate handler into your test automatically when recording against a dialog. You can also insert a dialog handler manually, however.

### Version 2015 R1 and later

As of version 2015 R1 you can find the dialog steps in the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a> under Dialogs section.

<table id="no-table">
<tr>
<td>![Standalone][22]<br>**Standalone Version**</td>
<td>![VS Plugin][23]<br>**VS Plugin**</td>
</tr>
<table>

### Version 2014 R4 and earlier

<table id="no-table">
<tr>
<td>![Standalone][1]<br>**Standalone Version**</td>
<td>![VS Plugin][2]<br>**VS Plugin**</td>
</tr>
<table>

## Alert

Displays a message and a single "OK" button.

<table id="no-table">
<tr>
<td>![Alert][3]</td><td>![Alert][4]</td>
</tr>
<tr>
<td>![Alert][5]</td><td>![Alert][6]</td>
</tr>
<table>

## Confirm

Displays a message and asks a question. 

<table id="no-table">
<tr>
<td>![Confirm][7]</td><td>![Confirm][8]</td>
</tr>
<tr>
<td>![Confirm][9]</td><td>![Confirm][10]</td>
</tr>
<table>

## Logon

Enters username, password, and click "OK".


<table id="no-table">
<tr>
<td>![Logon][11]</td><td>![Logon][12]</td>
</tr>
<tr>
<td>![Logon][13]</td><td>![Logon][14]</td>
</tr>
<table>

## Prompt

Asks to provide some additional information.

<table id="no-table">
<tr>
<td>![Prompt][15]</td><td>![Prompt][16]</td>
</tr>
<tr>
<td>![Prompt][17]</td><td>![Prompt][18]</td>
</tr>
<table>

## FileUpload

Inputs the path of a file to be uploaded to the server. 

![Upload][19]


Indicate multiple files for upload using space-separated quoted file paths.

![Upload][20]

## Download

Saves a file hosted on the server locally to disk.

![Download][21]

[1]: /img/features/dialogs-and-popups/dialogs/fig1.png
[2]: /img/features/dialogs-and-popups/dialogs/fig2.png
[3]: /img/features/dialogs-and-popups/dialogs/fig3.png
[4]: /img/features/dialogs-and-popups/dialogs/fig4.png
[5]: /img/features/dialogs-and-popups/dialogs/fig5.png
[6]: /img/features/dialogs-and-popups/dialogs/fig6.png
[7]: /img/features/dialogs-and-popups/dialogs/fig7.png
[8]: /img/features/dialogs-and-popups/dialogs/fig8.png
[9]: /img/features/dialogs-and-popups/dialogs/fig9.png
[10]: /img/features/dialogs-and-popups/dialogs/fig10.png
[11]: /img/features/dialogs-and-popups/dialogs/fig11.png
[12]: /img/features/dialogs-and-popups/dialogs/fig12.png
[13]: /img/features/dialogs-and-popups/dialogs/fig13.png
[14]: /img/features/dialogs-and-popups/dialogs/fig14.png
[15]: /img/features/dialogs-and-popups/dialogs/fig15.png
[16]: /img/features/dialogs-and-popups/dialogs/fig16.png
[17]: /img/features/dialogs-and-popups/dialogs/fig17.png
[18]: /img/features/dialogs-and-popups/dialogs/fig18.png
[19]: /img/features/dialogs-and-popups/dialogs/fig19.png
[20]: /img/features/dialogs-and-popups/dialogs/fig20.png
[21]: /img/features/dialogs-and-popups/dialogs/fig21.png
[22]: /img/features/dialogs-and-popups/dialogs/fig22.png
[23]: /img/features/dialogs-and-popups/dialogs/fig23.png




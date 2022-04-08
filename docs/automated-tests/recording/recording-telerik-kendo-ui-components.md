---
title: How to Record Steps for Telerik and Kendo UI Components 
page_title: How to Record Steps for Telerik and Kendo UI Components
description: "Test Studio records specific steps to 


handle the dialogs and popups generated from the tested application. How to record the test scenario if I need to download a file? Can I handle dialogs in Test Studio automatically? How to handle in Test Studio a popup opened in new window/tab. 

How to handle download dialog. How to handle upload dialog? How to handle confirm dialog? How to handle  alert dialog? How to handle logon dialog? How to handle prompt dialog? How to handle generic dialog? FileUpload dialog in Test Studio test."
position: 3
---
# How to Automate Application Built with Telerik and Kendo UI Components

Test Studio recording process recognizes the different dialogs generated from the automated page and detects what actions are taken to handle the dialog. These actions are represented as a single step in the test.

In this article you can find out more about dialog handling in Test Studio tests divided in few sections:

- [Alert, Confirm, Prompt Dialog Boxes](#alert-confirm-prompt-dialog-boxes)
- [Logon Dialog](#logon-dialog)
- [Download and Upload File Dialogs](#download-and-upload-file-dialogs)
- [Record in a Popup Window](#how-to-handle-a-popup-page-opened-in-new-tab)
- [Maintain the Handle Dialog and Connect to Popup Steps](#maintain-the-handle-dialog-and-popup-steps)

## How to Record a Dialog Displayed from the Tested Page

All sample pages used in this article are from the  <a href="https://www.w3schools.com/" target="_blank">W3School</a> platform.

Dialogs are automatically recorded in Test Studio test taking your actions as baseline. There is a dedicated step for each different dialog with various properties related to the specifics of the dialog - for example, download/upload file path or text, username, etc. When the tested page prompts any dialog, handle it as you would do without Test Studio and __Test Studio recorder will add the step__ for you.

> __Tip__
><br>
><br>
> If you experience any troubles with recording or executing the dialog steps, check if there is an available update in the <a href="/prerequisites/configure-your-browser/browser-support-updater" target="_blank">Latest Browser Support section</a> and apply it before you proceed.

### Alert, Confirm, Prompt Dialog Boxes

JavaScript generates three type of popup messages and these are as follows:

* __Alert__ - often used if some information is to be shared to the user. To proceed the user needs to click 'OK'.
* __Confirm__ - often used when the user needs to verify or accept something. The user needs to click either "OK" or "Cancel" to proceed.
* __Prompt__ - often used if the user should submit a value before entering a page. The user needs to click either "OK" or "Cancel" to proceed after entering the input value.

To try out these types of dialogs you can use the _'Try It Yourself'_ buttons on each example for the <a href="https://www.w3schools.com/js/js_popup.asp" target="_blank">W3School JavaScript Popup Boxes</a> page. Here are the steps recorded in a test for each of the dialog boxes.

<table id=no-table>
<tr>
<td>![Alert dialog](/img/automated-tests/recording/dialogs/alert-dialog-step.png)<br>__Handle Alert Dialog__</td>
</tr>
<table>

<table id=no-table>
<tr>
<td>![Confirm dialog](/img/automated-tests/recording/dialogs/confirm-dialog-step.png)<br>__Handle Confirm Dialog__</td>
</tr>
<table>

<table id=no-table>
<tr>
<td>![Prompt dialog](/img/automated-tests/recording/dialogs/prompt-dialog-step.png)<br>__Handle Prompt Dialog__</td>
</tr>
<table>

> __Tip__
><br>
><br>
> When handling such type of a dialog, usually there is something changed on the page (or remains unchanged depending on the scenario). You can use a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">verification step</a> to check if the expected outcome after handling the dialog is present.

### Logon Dialog

This is an authorization dialog, which requires the user to enter username and password in order to access the requested page. If the logon dialog is canceled or the entered credentials are incorrect, the page returns some sort of an error that the request is not authorized.

Due to the specifics of this dialog and the Test Studio recording process flow, this dialog requires some additional actions to be recorded. These are listed step by step in the below list:

1. Start the recording session and navigate to the page.
2. The page is not fully loaded until the logon dialog is handled. Thus the Test Studio recorder is not yet started and attached to the browser. Therefore, if you enter any username and password, these does not get recorded in the Test Studio test.
3. One option is to enter the valid credentials to login to the page and then <a href="/features/dialogs-and-popups/dialogs#add-a-handle-dialog-step-manually" target="_blank">manually insert the step to handle the Logon dialog.
4. The other option is to __first cancel the logon dialog__ - there is no step added in the test because the recorder is not yet active. Once the page returns the message that access is denied, the Test Studio recorder gets attached to the browser. On __manually refreshing the page__ from the browser, the __logon dialog prompts again__ and this time, while you enter your credentials to access the page, Test Studio __records your actions and adds the step__ in the test.

<table id=no-table>
<tr>
<td>![Logon dialog](/img/automated-tests/recording/dialogs/logon-dialog-step.png)<br>__Handle Logon Dialog__</td>
</tr>
<table>

### Download and Upload File Dialogs

The __Upload__ dialog brings up the File Explorer window and let's you choose a file from the local disc to upload to the tested server.

<table id=no-table>
<tr>
<td>![Upload dialog](/img/automated-tests/recording/dialogs/upload-dialog-step.png)<br>__Handle Upload Dialog__</td>
</tr>
<table>

The __Download__ dialog is typically a sequence of dialogs - the browser prompts to download a file and the File Explorer lets you choose the destination path. Although the _'Save As'_ option for the download procedure in the browsers differs, Test Studio recognizes this and records a single __Handle Download dialog__ step. This step covers the complete sequence of dialogs for each browser including the prompt message that the __file already exists__ in the destination folder - the file is overwritten.

<table id=no-table>
<tr>
<td>![Download dialog](/img/automated-tests/recording/dialogs/download-dialog-step.png)<br>__Handle Download Dialog__</td>
</tr>
<table>

> __Tip__
><br>
><br>
> Part of the <a href="/prerequisites/configure-your-browser/browser-configuration" target="_blank">browsers calibration settings</a> is to __disable the automatic download__ of files. Thus, if calibrated, the browser always asks where to save the file. In case you don't see the option to choose the destination folder where to save the file, __ensure the browser is calibrated__ and re-record the test scenario.

## How to Handle a Popup Page Opened in New Tab

The __HTML popup windows or tabs are automatically detected by Test Studio__. Depending on the browser these will be open either in a new window (IE), or a new tab (Chrome, Edge, Firefox). In the case when this is a new window, a new Test Studio recorder toolbar is initiated for the new window. In the case when the new page is opened in new tab, Test Studio recorder focus is switched to this new tab until it gets closed.

When recording such scenario Test Studio recorder automatically adds a __'Connect to popup'__ step when this is detected, then fetches the actions performed in the new window/tab, and once this gets closed, Test Studio adds a __'Close popup'__ step.

![Connect to popup step](/img/automated-tests/recording/dialogs/popup-steps.png)

Test Studio uses the URL of the new window/tab to connect to it. If the URL is randomly generated, you can use only part of it by enabling the checkbox 'IsUrlPartial'.

> __Note__
><br>
><br>
> Keeping the two windows/tabs opened and switching multiple times between these is not a supported scenario.

## Maintain the Handle Dialog and Popup Steps

Test Studio predefined step properties for handling dialog and popus are meant to cover common scenarios without any further adjustments. However, you might face any sort of specific case for which you need to fine tune the default step properties. Find out more about these in the below links:

- <a href="/features/dialogs-and-popups/dialogs" target="_blank">Handle Dialog Steps</a> - How to add a dialog step manually and what properties can be changed.
- <a href="/features/dialogs-and-popups/html-popups" target="_blank">Handle Popup Steps</a> - How to add a popup step manually and what properties can be changed.

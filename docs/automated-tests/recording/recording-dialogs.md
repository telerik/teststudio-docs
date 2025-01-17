---
title: How to Record Dialogs and Popups 
page_title: How to Handle Dialogs and Popups during Test Recording
description: "Test Studio records specific steps to handle the dialogs and popups generated from the tested application. How to record the test scenario if I need to download a file? Can I handle dialogs in Test Studio automatically? How to handle in Test Studio a popup opened in new window/tab. 
How to handle download dialog. How to handle upload dialog? How to handle confirm dialog? How to handle  alert dialog? How to handle logon dialog? How to handle prompt dialog? How to handle generic dialog? FileUpload dialog in Test Studio test."
position: 3
---
# How to Handle Dialogs and Popups Generated from the Tested Page

Test Studio recording process recognizes the dialogs generated from the automated application and detects how the user handles the dialog. These actions are represented as a single step in the test.

In this article you can find out more about dialog handling in Test Studio tests divided in few sections:

- [How to Handle Dialogs and Popups Generated from the Tested Page](#how-to-handle-dialogs-and-popups-generated-from-the-tested-page)
  - [How to Record a Dialog Displayed from the Tested Application](#how-to-record-a-dialog-displayed-from-the-tested-application)
  - [Alert, Confirm, Prompt Dialog Boxes](#alert-confirm-prompt-dialog-boxes)
  - [Logon Dialog](#logon-dialog)
  - [Download and Upload File Dialogs](#download-and-upload-file-dialogs)
    - [Upload Dialog](#upload-dialog)
    - [Download Dialog](#download-dialog)
  - [How to Handle a Popup Page Opened in New Tab](#how-to-handle-a-popup-page-opened-in-new-tab)
  - [Maintain the Handle Dialog and Popup Steps](#maintain-the-handle-dialog-and-popup-steps)

## How to Record a Dialog Displayed from the Tested Application

All sample web pages used in this article are from the  <a href="https://www.w3schools.com/" target="_blank">W3School</a> platform.

Handling a dialog is automatically recorded in Test Studio test taking your actions as baseline. Each different dialog is handled via a separate step, which introduces various properties related to the specifics of the dialog - for example, download/upload file path or text, username, etc. When the tested page prompts any dialog, handle it as you would do without Test Studio and __Test Studio recorder will add the step__ for you.

> __Tip__
><br>
><br>
> If you experience any troubles with recording or executing the dialog steps, check if there is an available update in the <a href="/prerequisites/configure-your-browser/browser-support-updater" target="_blank">Latest Browser Support section</a> and apply it before you proceed.

## Alert, Confirm, Prompt Dialog Boxes

JavaScript generates three type of popup messages and these are as follows:

* __Alert__ - often used if some information is to be shared to the user. The user has the only option to click 'OK'.

    ![Alert Dialog](/img/automated-tests/recording/dialogs/alert-dialog.png)

* __Confirm__ - often used when the user needs to verify or accept something. The user has the option to click either "OK" or "Cancel" to handle the dialog.

    ![Confirm dialog](/img/automated-tests/recording/dialogs/confirm-dialog.png)

* __Prompt__ - often used if the user should submit a value before entering a page. The user has the option to enter the input value and then to click either "OK" or "Cancel". 

    ![Prompt dialog](/img/automated-tests/recording/dialogs/prompt-dialog.png)


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
> When handling such type of a dialog, usually there is something changed on the page (or remains unchanged depending on the scenario). You can __use a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">verification step</a> to check if the expected outcome__ after handling the dialog is present.

## Logon Dialog

This is an authorization dialog, which requires the user to enter username and password in order to access the requested page. If the logon dialog is canceled or the entered credentials are incorrect, the page returns some sort of an error that the request is not authorized.

Due to the specifics of this dialog and the Test Studio recording process flow, this dialog requires some additional actions to be recorded. These are listed step by step in the below list:

1. Start the recording session and navigate to the page.
2. The page is not fully loaded until the logon dialog is handled. Thus the Test Studio recorder is not yet started and attached to the browser. Therefore, if you enter any username and password, these does not get recorded in the Test Studio test.
3. One option is to enter the valid credentials to login to the page and then <a href="/features/dialogs-and-popups/dialogs#add-a-handle-dialog-step-manually" target="_blank">manually insert the step to handle the Logon dialog</a>.
4. The other option is to __first cancel the logon dialog__ - there is no step added in the test because the recorder is not yet active. Once the page returns the message that access is denied, the Test Studio recorder gets attached to the browser. On __manually refreshing the page__ from the browser, the __logon dialog prompts again__ and this time, while you enter your credentials to access the page, Test Studio __records your actions and adds the step__ in the test.

<table id=no-table>
<tr>
<td>![Logon dialog](/img/automated-tests/recording/dialogs/logon-dialog-step.png)<br>__Handle Logon Dialog__</td>
</tr>
<table>

## Download and Upload File Dialogs

The Download and Upload file actions usually require more than one single interaction with the dialog. Test Studio recording process detects the user actions to choose a folder and file and represents these into a single step to handle the dialog. 

> __Note__
><br>
><br>
> The __user needs to have read/write permissions for the folders__ in which is the file to upload or save. Check here if you get prompted for insufficent permissions 

### Upload Dialog 

The Upload File opens a __Open__ dialog in Windows File Explorer in which the user browses to a specific folder and selects a specified file to be uploaded. 

![Upload dialog](/img/automated-tests/recording/dialogs/upload-dialog.png)

Test Studio fetches the selected folder and file and automatically populates the complete file path into the __Handle Upload dialog__ step. 

<table id=no-table>
<tr>
<td>![Upload dialog](/img/automated-tests/recording/dialogs/upload-dialog-step.png)<br>__Handle Upload Dialog__</td>
</tr>
<table>

> __Tip!__
><br>
><br>
> If the user selects any system folder which can be replaced with a <a href="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" target="_blank">recognized system variable</a> __Test Studio automatically converts the path using the respective system variable__
><br>
><br>
> For example, if the user selects a destination folder under the current Windows user folder __Test Studio automatically converts the path using the Windows variable %USERPROFILE%__.

### Download Dialog

The Download File dialog opens a __SaveAs__ dialog in Windows File Explorer in which the user browses to a specific folder and enters name for the file to be downloaded. 

![Download dialog](/img/automated-tests/recording/dialogs/download-dialog.png)

Handling of a download dialog typically requires handling a sequence of dialogs - the browser prompts to download a file and the File Explorer lets you choose the destination path; optionally, handling a prompt message that a file with the same name already exists in the selected folder - the existing file is overwritten in such case. Test Studio fetches all actions taken and automatically records the __Handle Download dialog__ step and populates the complete file path and name. 

<table id=no-table>
<tr>
<td>![Download dialog](/img/automated-tests/recording/dialogs/download-dialog-step.png)<br>__Handle Download Dialog__</td>
</tr>
<table>

> __Tip!__
><br>
><br>
> If the user selects any system folder which can be replaced with a <a href="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" target="_blank">recognized system variable</a> __Test Studio automatically converts the path using the respective system variable__
><br>
><br>
> For example, if the user selects a destination folder under the current Windows user folder __Test Studio automatically converts the path using the Windows variable %USERPROFILE%__.

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

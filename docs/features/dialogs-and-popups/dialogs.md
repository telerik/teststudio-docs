---
title: Properties for Dialog Handling Steps
page_title: Dialog Handling Steps in Test Studio
description: "Can I set the time to wait for a dialog to be handled. Dialog handling Timeouts and properties. Add a handle dialog step manually."
position: 0
---
# Dialog Handling Steps

<a href="/automated-tests/recording/recording-dialogs" target="_blank">Recording dialogs</a> is an out-of-the-box feature in Test Studio. The steps recorded for the dialogs provide various properties to fine tune the execution. The steps to handle dialogs can be added also manually in the test.

In this article you can find useful information about:

- [Dialog Handling Steps](#dialog-handling-steps)
  - [Add a Handle Dialog Step Manually](#add-a-handle-dialog-step-manually)
  - [Properties for Handle Dialog Steps](#properties-for-handle-dialog-steps)
  - [Timeouts](#timeouts)
  - [Handle Button](#handle-button)
  - [Download and Upload Paths in Web Test](#download-and-upload-paths-in-web-test)
  - [SaveFile and OpenFile Paths in WPF Test](#savefile-and-openfile-paths-in-wpf-test)

## Add a Handle Dialog Step Manually

Even if you work on the tests in the project and have no active recording session, you can add the specific steps to handle a dialog from the <a href="/features/custom-steps/overview#add-a-general-step-from-the-step-builder" target="_blank">Step Builder</a>. All dialog steps are listed under the General section of the Step Builder, under __Dialogs__. Select the type of dialog to handle and add hit the __Add Step__ button.

![Step Builder Dialogs section][1]

## Properties for Handle Dialog Steps

The various properties allows you to fine tune the steps to handle dialogs across the automated page.

## Timeouts

The properties common for all dialogs are the __HandleTimeout__ - controls the time, which the test waits for the dialog to be handled, and the __InitializationTime__ - controls the time, which the test waits before it starts searching for such dialog. It is useful to increase these when it takes longer time for the dialog to appear, or to be finished (usually for the handle download dialogs, when the file to download is too large).

![Dialog steps timeouts][2]

## Handle Button

Each dialog step gives the option to change the button used to handle it during recording, or to adjust it if added manually.

![Dialog handle button][3]

The dropdown list provides all possible options for a button to handle a dialog. If you choose wrong type of button for the specific step, there is a prompt message to inform you which are the possible dismiss options for this dialog.

![Choosing wrong handle button][4]

## Download and Upload Paths in Web Test

The __DownloadPath__ and __FileUploadPath__ properties are mandatory for the respective type dialog. They require a valid full path to the file to interact with.

![File Locations][5]

> __Tip!__
><br>
><br>
> If the user selects any system folder which can be replaced with a <a href="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" target="_blank">recognized system variable</a> __Test Studio automatically converts the path using the respective system variable__
><br>
><br>
> For example, if the user selects a destination folder under the current Windows user folder __Test Studio automatically converts the path using the Windows variable %USERPROFILE%__.

The __FileUploadPath__ accepts multiple files listed quoted and space separated. These will be uploaded if the server accepts multiple files upload.

![Multiple files upload][6]

## SaveFile and OpenFile Paths in WPF Test

The __FilePath__ property is mandatory for the __SaveFile__ and __OpenFile__ dialogs. They require a valid full path to the file to interact with.

![FilePath property in WPF SaveFile][7]

> __Tip!__
><br>
><br>
> If the user selects any system folder which can be replaced with a <a href="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" target="_blank">recognized system variable</a> __Test Studio automatically converts the path using the respective system variable__
><br>
><br>
> For example, if the user selects a destination folder under the current Windows user folder __Test Studio automatically converts the path using the Windows variable %USERPROFILE%__.

The __FilePath__ property in __OpenFile__ dialog accepts multiple files listed quoted and space separated. These will be uploaded if the server accepts multiple files upload.

![FilePath property in WPF OpenFile][8]

[1]: /img/features/dialogs-and-popups/dialogs/dialog-step-builder.png
[2]: /img/features/dialogs-and-popups/dialogs/timeouts-extended-menu.png
[3]: /img/features/dialogs-and-popups/dialogs/handle-button.png
[4]: /img/features/dialogs-and-popups/dialogs/button-warning.png
[5]: /img/features/dialogs-and-popups/dialogs/download-path.png
[6]: /img/features/dialogs-and-popups/dialogs/file-upload-extended-menu.png
[7]: /img/features/dialogs-and-popups/dialogs/filepath-in-savefile-dialog.png
[8]: /img/features/dialogs-and-popups/dialogs/open-file-dialog-multiple-file.png
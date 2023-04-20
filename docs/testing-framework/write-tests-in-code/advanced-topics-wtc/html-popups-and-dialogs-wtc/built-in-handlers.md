---
title: Built-In Dialog Handlers
page_title: Built-In Dialog Handlers
description: "Test Studio and its underlaying Testing Framework lets you handle dialogs produced from the browser, or the WPF or Desktop application out-of-the-box. There are different built-in handlers to use for handling the different dialogs."
position: 0
---
# Built-In Handlers 

__Telerik Testing Framework__ ships with native support for HTML pop-ups and built-in dialog handling framework (under the _ArtOfTest.WebAii.Win32.Dialogs_ namespace) with handlers for the common browser dialogs like Alert, Prompt and Confirm, Upload and Download dialogs, and Logon dialogs, WPF dialogs. The framework also enables you to extend this support to handle any custom dialogs in the specific manner you need.

Below is a list with references on how to handle each popup or specific dialog.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/html-popups" target="_blank">HTML Pop-ups</a> - New browser instance or tab, which is invoked by an action on the current page.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/javascript-dialogs" target="_blank">Alert Dialogs</a> -  You only need to define how the dialog should be handled.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/confirm-dialogs" target="_blank">Confirm Dialogs</a> -  You only need to define how the dialog should be handled.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/prompt-dialogs" target="_blank">Prompt Dialogs</a> -  You only need to define how the dialog should be handled.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/win32-dialogs" target="_blank">Logon Dialogs</a> - It is not a browser window, but a dialog displayed by the Windows operating system.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/file-upload-dialog" target="_blank">File Upload Dialogs</a> - You need to pass in the full path to the file to upload and how the dialog should be handled.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/file-download-dialog" target="_blank">Downloads File Dialogs </a> - You have a number of classes included that make handling of the file download dialogs very easy.

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/modal-dialogs" target="_blank">Modal Dialogs</a> - Don't act like standard HTML pop-up windows and require special handling

* <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/custom-dialogs" target="_blank">Handle Custom Dialogs </a> - You can craft your own dialog handling code and then ask the dialog to call your code instead of its dialog handling code.



There are a few things to note about dialog handing:

* The dialog monitor can take 1-N dialogs and they can be added/removed at any point in your test code regardless of whether the monitoring has started or not.

* Notice how each dialog takes in an instance of a parent browser that will eventually produce the dialog. Before handling each dialog the DialogMonitor makes sure that the current dialog to be handled belongs to that browser instance. This is done to ensure the integrity of handling and to limit the chances the DialogMonitor could match a browser that looks similar to the dialog it needs to handle. Also this is needed in multi browser support scenarios.
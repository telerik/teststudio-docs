---
title: Built-In Handlers
page_title: Built-In Handlers
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Built-In Handlers#

Telerik Testing Framework includes native support for HTML pop-ups for all supported browsers in addition to a dialog handling framework (under the Win32.Dialogs) namespace with built-in support to handle some of the common browser dialogs like JavaScript Alert, Upload dialog and Logon dialog. The framework also enables you to extend this support to handle any custom dialog you need handled in any manner.


<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/html-popups" target="_blank">HTML Pop-ups</a> -  Browser instances that are invoked by some action on an element of the page.
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/modal-dialogs" target="_blank">Modal Dialogs</a> - Don't act like standard HTML pop-up windows and require special handling
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/JavaScript-dialogs" target="_blank">Alert Dialogs</a> -  You only need to define how the dialog should be handled.
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/win32-dialogs" target="_blank">Logon Dialogs</a> - It is not a browser window, but a dialog displayed by the Windows operating system.
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/file-upload-dialog" target="_blank">FileUpload Dialog</a> - You need to pass in the full path to the file to upload and how the dialog should be handled.
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/file-download-dialog" target="_blank">Handling File Downloads</a> - You have a number of classes included that make handling of the file download dialogs very easy.
 
<a href="/code-in-test/advanced-topics-wtc/html-popups-and-dialogs-wtc/custom-dialogs" target="_blank">Custom Dialog Handler</a> - You can craft your own dialog handling code and then ask the dialog to call your code instead of its dialog handling code.

There are a few things to note about dialog handing:

* The dialog monitor can take 1-N dialogs and they can be added/removed at any point in your test code regardless of whether the monitoring has started or not.

* Notice how each dialog takes in an instance of a parent browser that will eventually produce the dialog. Before handling each dialog the DialogMonitor makes sure that the current dialog to be handled belongs to that browser instance. This is done to ensure the integrity of handling and to limit the chances the DialogMonitor could match a browser that looks similar to the dialog it needs to handle. Also this is needed in multi browser support scenarios.
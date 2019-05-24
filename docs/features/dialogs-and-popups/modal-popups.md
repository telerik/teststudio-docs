---
title: Modal Popups
page_title: Modal Popups
description: "There is a modal popup displayed in the tested page - how can I automate modal popup windows in Test Studio tests. Connect to modal popup window during Test Studio test run/execution"
previous_url: /user-guide/dialogs-and-popups/modal-popups.aspx, /user-guide/dialogs-and-popups/modal-popups
position: 1
---
# Modal Popups


A Modal Popup window is a child window that requires users to interact with it before they can return to operating the parent application. Modal windows often have a different appearance than normal windows and are typically without navigation buttons and menu headings.


Modal Popups are detected automatically by Test Studio, like HTML Popups, however a separate [Recording Toolbar](/getting-started/test-recording/recording-toolbar) is not attached.

![Modal Window][1]

Notice the *Connect to modal pop-up window* and *Close modal pop-up window* steps. There are additional attributes in the Properties pane under the Modal Popup heading.

- IsModalPopup identifies whether the popup window is modal.
- ModalPopupPartialCaption locates the desired modal popup based on its partial caption.


> Test Studio cannot connect to Modal Popups which do not have a title in Firefox, Safari, and Chrome. Ensure all Modal Popups are titled if you are testing in browsers other than Internet Explorer.

![Modal Window Test][2]

[1]: /img/features/dialogs-and-popups/modal-popups/fig1.png
[2]: /img/features/dialogs-and-popups/modal-popups/fig2.png


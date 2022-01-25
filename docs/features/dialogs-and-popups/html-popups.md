---
title: Properties for Handling Popup Steps
page_title: Connect to and Close Popup Steps in Test Studio
description: "Can I modify the steps which connect to popup window during Test Studio test run? Can I add a Connect to popup step manually? How can I connect to a modal popup? Can I connect to a popup with dynamic URL?

Use the properties of Connect to and Close Popup steps to fine tune the execution of Test Studio tests when handling popup windows. "
position: 1
---
# Connect and Close Popup Steps

<a href="#how-to-handle-a-popup-page-opened-in-new-tab" target="_blank">Detecting popups opened in new window</a> is an out-of-the-box feature in Test Studio. The steps recorded for connecting to and closing the popups provide various properties to fine tune the execution. The steps to connect to a popup and then close it, can be added also manually in the test.

In this article you can find useful information about:

- [Add manually a step to connect to/close popup](#add-a-connectclose-popup-step-manually)
- [Connect to/Close popup steps timeouts](#timeouts)
- [Popup URL properties in the connect to/close popup steps](#popup-url)
- [How to connect to popup with dynamic URL?](#popups-with-dynamic-url)
- [What are modal popups and how Test Studio handles these?](#modal-popups)

## Add a Connect/Close Popup Step Manually

Even if you work on the tests in the project and have no active recording session, you can still add the specific steps to connect to and close a popup from the <a href="/features/custom-steps/overview#add-a-general-step-from-the-step-builder" target="_blank">Step Builder</a>. These steps are listed under the General section of the Step Builder, under __Dialogs__. Select one of the __Connect/Close popup window__ step and add hit the __Add Step__ button.

![Step Builder Connect/Close popup steps](/img/features/dialogs-and-popups/html-popups/step-builder-popup-steps.png)

## Properties for Connect/Close Popup Steps

The various properties allows you to fine tune the steps to connect and close popups in the automated application.

## Timeouts

The properties related to timing are the __PopupWaitTimeout__ - this controls the time, which the tests waits for the popup to appear, and the __InitializationTime__ - it controls the time, which the test waits before it starts searching for such dialog (applicable for IE browser only). It is useful to increase this, if the popup window/tab requires longer time to popup.

![Timoeouts for Connect/Close popup steps](/img/features/dialogs-and-popups/html-popups/popup-steps-timeouts.png)

## Popup URL

Test Studio recognizes the new popup windows by their URLs and records the current URL into the __PopupUrl__ step property.

![PopupURL for Connect/Close popup steps](/img/features/dialogs-and-popups/html-popups/popup-steps-url-properties.png)

> __Note__
><br>
><br>
> There's a limitation in Test Studio in that it cannot tell the difference between the parent window and the popup window when the URL is the same. Test Studio will randomly connect to the right or wrong one and you cannot control it.

## Popups with Dynamic URL

Test Studio allows you to use only part of the URL of a popup window. In the cases when the tested web application typically loads popups with URLs that contain a dynamic portion, such as a search query, you can use the __IsUrlPartial__ step property to alter the settings of how the popup is matched.

For example:

- Your Popup URL contains a dynamic query: http://www.domain.com/search?1234567890
- Set **IsUrlPartial** to True.
- Set **PopupUrl** to: http://www.domain.com/search

![Popup with dynamic URL for Connect/Close popup steps](/img/features/dialogs-and-popups/html-popups/popup-dynamic-url.png)

## Modal Popups

A Modal popup window is a __child window that requires users to interact with it before they can return to operating the parent application__. Modal windows often have a different appearance than normal windows and are typically without navigation buttons and menu headings.

![Modal Window](/img/features/dialogs-and-popups/html-popups/fig1.png)

Test Studio __detects automatically also this type of popups__, but due to their specific behavior, there is no additional recorder loaded for these modal windows. They are recognized in Test Studio by their modal caption and for them the _Connect to/Close pop-up window_ steps can be modified to use the properties __IsModalPopup__, which transforms the step to search for modal window, and the __ModalPopupPartialCaption__, which holds the modal window caption name (can use partial caption).

![Connect to Modal Popup](/img/features/dialogs-and-popups/html-popups/modal-popup.png)

> __Note__
><br>
><br>
> Test Studio cannot connect to modal popup windows which do not have a title in Firefox, Safari, and Chrome. To avoid any troubles in automating the tested page in browsers other than Internet Explorer, ensure any modal popups are titled.

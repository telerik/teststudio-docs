---
title: HTML Popups
page_title: HTML Popups
description: "There is a popup displayed in the tested page - how can I automate popup windows in Test Studio tests. Connect to popup window during Test Studio test run/execution"
previous_url: /user-guide/dialogs-and-popups/html-popups.aspx, /user-guide/dialogs-and-popups/html-popups
position: 1
---
# HTML Popups

HTML Popups are automatically detected by Test Studio. It displays the popup window with its own [Recording Toolbar](/getting-started/test-recording/recording-toolbar). Test Studio automatically includes test steps for connecting to, recording+ steps inside the new browser window, and finally closing the HTML Popup.

![Popup Windows][1]

The sequence is typically like the test steps shown below.

1. The popup window is connected.
1. Actions and/or verifications are performed inside the new browser window.
1. The popup window is closed.

![Popup Test Steps][2]

The properties for the Connect to pop-up window step (test step 3) are shown below:

![Popup Test Steps][3]

> There's a limitation in Test Studio in that it cannot tell the difference between the parent window and the popup window when the URL is the same. Test Studio will randomly connect to the right or wrong one and you cannot control it.

## Popups with Dynamic Queries


If your web application typically loads popups with URLs that contain a dynamic portion, such as a search query, you will need to alter the Connect to pop-up window step properties. 

For example:

- Your Popup URL contains a dynamic query: http://www.domain.com/search?1234567890
- Set **IsUrlPartial** to True.
- Set **PopupUrl** to: http://www.domain.com/search


[1]: /img/features/dialogs-and-popups/html-popups/fig1.png
[2]: /img/features/dialogs-and-popups/html-popups/fig2.png
[3]: /img/features/dialogs-and-popups/html-popups/fig3.png
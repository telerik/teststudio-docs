---
title: DOM Explorer
page_title: DOM Explorer
description: DOM Explorer
publish: true
position: 4
slug: ms-dom-explorer
previous_url: /test-studio-mobile/getting-started-mb/dom-explorer,/test-studio-mobile/getting-started-mb
---
#DOM Explorer

 > The DOM explorer is populated only when a test is in record mode.

The DOM Explorer allows you to inspect all elements of the tested application at once, shown in a tree-like or in a grouped-by-tag view. The DOM Explorer is helpful with a complex applications where simply taping may not be enough to find the element you're looking for. It is used also for building steps through the [Step Builder]({% slug ms-step-builder%})

In order to access it click **DOM Explorer** tab in the middle bottom pane.

![DOM Explorer](/img/test-studio-mobile/getting-started-mb/dom-explorer/fig1.png)

##DOM Explorer Toolbar

The DOM Explorer Toolbar provides some additional features that may come handy.

![Toolbar](/img/test-studio-mobile/getting-started-mb/dom-explorer/fig2.png)

*	**Highlight the element** - toggle this button whether to highlight the element in the tested application or not. When it is enabled the selected element from the DOM tree will be surrounded by a red rectangle on the recording device. This feature works only for Native apps.

*	**Search for element** - to search an element in the DOM. The found element will be selected automatically.

*	**Elements Tree View** - displays elements in their original tree-like hierarchy order.

*	**Elements Tag View** - displays elements grouped by their tagname.

*	**View Selector** - displayed only when Hybrid test is in record mode. Use it to select the Native/Web view which DOM tree you need loaded.


## See also

* [Record an Android test]({% slug ms-record-test-android%})
* [Record an iOS test]({% slug ms-record-test-ios%})
* [Record a Web test]({% slug ms-record-test-web%})
* [Record Android Hybrid Test]({% slug ms-record-test-android-hybrid%})
* [Record iOS Hybrid Test]({% slug ms-record-test-ios-hybrid%})
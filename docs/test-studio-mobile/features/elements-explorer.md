---
title: Elements Explorer
page_title: Elements Explorer
description: Elements explorer functionality
slug: ms-elements-explorer
tags: elements, explorer, mobile
publish: true
position: 3
previous_url: /test-studio-mobile/getting-started-mb/elements-explorer
---
#Elements Explorer

This section is dedicated to the Elements Explorer view and functionality.

The Elements Explorer pane shows a tree-like view of your elements in the project. Elements are grouped first by test and then by a test view in the test forming hierarchical representation. Elements are added to the tree when test steps are recorded based on the views the user interacts with. 

![Mobile Studio Elements Explorer](/img/test-studio-mobile/getting-started-mb/elements-explorer/mobile-studio-elements-explorer.png)

Right click an element or a view to show context menu options:

* **Renaming** an element or a view to give it a descriptive name for better recognition in the tree.

* **Edit** an element. Using this option the element find logic can be changed in the query builder dialog. At the time elements are added to the repository, they are assigned a query that is used to identify the same element when the test is played back. Change that query if the element identification is not recorded as expected or wrong element is identified. The query builder dialog initially shows the current query properties. Those properties are editable and can be deleted or new properties can be added to extend the query.

* Click **Used By** to see the list of steps of the current test where the selected element is used by. Double clicking a step from the list opens the test and highlights the step.

![Mobile Studio Query Builder](/img/test-studio-mobile/getting-started-mb/elements-explorer/mobile-studio-query-builder.png)

In the top left corner of the elements explorer pane, two buttons are located:

* **Refresh** elements button. In addition to refreshing the elements tree, this button will also collapse all expanded tests and views in the Elements explorer pane.

* Toggle highlighting button. When enabled this option automatically navigates the Elements explorer pane to the element used by the selected step. For example if the fourth step in the test uses element named `First slider`, then clicking on that step will automatically expand the elements tree to the `First slider` element and highlight it.

![Mobile Studio Toggle Highlight](/img/test-studio-mobile/getting-started-mb/elements-explorer/mobile-studio-toggle-highlight.png)

The Top right corner of the Elements explorer pane is reserved for visibility controlling buttons. The pane can be docked, pinned or closed. In addition it can be moved by drag-drop of its header or resized by drag-drop of its borders.

![Mobile Studio Elements Drag](/img/test-studio-mobile/getting-started-mb/elements-explorer/mobile-studio-elements-drag.png)

If the Elements explorer pane is accidently closed or in case a layout reset is needed, the View menu can be used

![Mobile Studio View Menu](/img/test-studio-mobile/getting-started-mb/elements-explorer/mobile-studio-view-menu.png)

See Also
--------

* [Getting Started Native Apps]({% slug ms-getting-started-native%})
* [Getting Started Web Apps]({% slug ms-getting-started-web%})
* [Test Explorer]({% slug ms-test-explorer%})
* [Project Explorer]({% slug ms-project-explorer%})
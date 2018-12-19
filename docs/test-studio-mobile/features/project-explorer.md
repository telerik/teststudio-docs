---
title: Project Explorer
page_title: Project Explorer
description: Project explorer functioanlity
slug: ms-project-explorer
tags: project, explorer, mobile
publish: true
position: 1
previous_url: /test-studio-mobile/getting-started-mb/project-explorer
---

#Project Explorer

This section is dedicated to the Project Exlorer UI and functionality.

The Project Explorer pane shows a tree-like structure of your tests in the project. Tests can be added directly to the project, or logically grouped in folders. Folders in turn, can be nested forming hierarchical representation of your testing solution. Tests and folders can be added either through the dedicated buttons located right above the project icon, or by a context menu shown on right click of a test, folder or project:

<table id="no-table">
	<tr>
		<td>![Mobile Studio Context Menu](/img/test-studio-mobile/getting-started-mb/project-explorer/mobile-studio-context-menu.png)</td>
		<td>![Context Menu](/img/test-studio-mobile/getting-started-mb/project-explorer/fig6.png)</td>
	</tr>
<table>


The context menu options (based on the target) also feature:

* Rename a project, folder, test or test list.
* Delete, Cut, Copy and Paste operations of a folder or test.
* Open a project, folder, test or test list in Windows explorer.
* Open a test or test list in Test Explorer.
* Open References in [Project Settings]({% slug ms-project-settings%}) where you can see a list of existing project references, add a new reference, or delete an existing one. 
* Add [Code Item]({% slug ms-code-item%})
* Add [Code-Behind File]({% slug ms-code-behind%})

Tests and folders support drag-drop to change the logical structure of the project:

![Mobile Studio Drag Drop](/img/test-studio-mobile/getting-started-mb/project-explorer/mobile-studio-drag-drop.png)
 
Project explorer also features keyboard support that includes:

* Selection navigation amongst tests and folders with the **arrow keys** (up and down).
* Expanding and collapsing parent folders with the **arrow keys** (left and right).
* Cut (Ctrl+X), Copy (Ctrl+C) and Paste (Ctrl+V) of folders and tests.
* Opening a selected test with **Enter** key.
* Deleting a test or folder with the **Delete** key.
* Renaming project, folder or test with **F2** key.
* Multi item selection using the Ctrl or Shift keys.

Searching through tests is supported by a search field at the top right corner of the pane. The search text is dynamic and once typing starts, items will be filtered with every key stroke.

![Mobile Studio Search Field](/img/test-studio-mobile/getting-started-mb/project-explorer/mobile-studio-search-field.png)

The Top right corner of the Project explorer pane is reserved for visibility controlling buttons. The pane can be docked, pinned or closed. In addition it can be moved by drag-drop of its header or resized by drag-drop of its borders.

![Mobile Studio Project Drag](/img/test-studio-mobile/getting-started-mb/project-explorer/mobile-studio-project-drag.png)

If the Project explorer pane is accidently closed or in case a layout reset is needed, the View menu can be used

![Mobile Studio View Menu](/img/test-studio-mobile/getting-started-mb/project-explorer/mobile-studio-view-menu.png)

See Also
--------

* [Getting Started Native Apps]({% slug ms-getting-started-native%})
* [Getting Started Web Apps]({% slug ms-getting-started-web%})
* [Test Explorer]({% slug ms-test-explorer%})
* [Elements Explorer]({% slug ms-elements-explorer%})
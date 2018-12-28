---
title: Project Explorer
page_title: Project Explorer
description: "Progress® Test Studio® for APIs - Project explorer functionality"
tags: project, explorer, mobile
publish: true
position: 0
---

# Project Explorer

The Project Explorer pane shows a tree-like structure of your tests in the project. Tests can be added directly to the project, or logically grouped in folders. Double click opens the test. Folders in turn, can be nested forming hierarchical representation of your testing solution.

Drag and drop test cases, folders and code items to **reorder** them. (*Ordering is supported since version R3 2017. Prior versions display and execute tests in alphabetical order.*)

Each project file has a context menu with further actions that can be taken. Note that some context menu items will show up only for certain project file types.

* Project Item

 ![Project][1]

 * Add New Test - create a new test under the project root.
 * Create Folder - create a folder under the project root.
 * Paste - paste all copied/cut files/folders.
 * Run - run all test in the project recursively.
 * Close Project - close the current project.
 * Open Folder in Windows Explorer - launch an explorer window with the project path loaded.

* Folder Item

 ![Folder][2]

 * Add New Test - create a new test under the selected folder.
 * Create Folder - create a folder under the selected folder.
 * Cut - keyboard shortcut is Ctrl+X.
 * Copy - keyboard shortcut is Ctrl+C.
 * Paste - keyboard shortcut is Ctrl+V.
 * Run Suite - run all test in the folder recursively.
 * Rename - edit the name of the folder.
 * Delete - Delete the folder.
 * Open Folder in Windows Explorer - launch an explorer window with the folder path loaded.

* Test Item

 ![Test][3]

 * Open - open the test.
 * Add Step - open a submenu to select a step to add.
 * Cut - keyboard shortcut is Ctrl+X.
 * Copy - keyboard shortcut is Ctrl+C.
 * Paste - keyboard shortcut is Ctrl+V.
 * Run Test - run the test.
 * Delete - delete the test
 * Rename - edit the name of the test.
 * Show in Windows Explorer - launch an explorer window with the folder path loaded.

* Step Item

 ![Step][4]

 * Open - open the step.
 * Cut - keyboard shortcut is Ctrl+X.
 * Copy - keyboard shortcut is Ctrl+C.
 * Paste - keyboard shortcut is Ctrl+V.
 * Run Step - run the step.
 * Run From Here - run all steps from the current step.
 * Run To Here - run all steps to the current step including it.
 * Rename - edit the name of the step.
 * Delete - delete the step

 Project explorer also features keyboard support that includes:

* Selection navigation amongst tests and folders with the **arrow keys** (up and down).
* Expanding and collapsing parent folders with the **arrow keys** (left and right).
* Cut (Ctrl+X), Copy (Ctrl+C) and Paste (Ctrl+V) of folders and tests.
* Opening a selected test with **Enter** key.
* Deleting a test or folder with the **Delete** key.
* Renaming project, folder or test with **F2** key.
* Multi-item selection using the Ctrl or Shift keys.
* Drag&drop steps, tests and folders. You are able to order the steps as you drag&drop them.
* Project items provide status after execution of the step/test.

 You are able to create a step, test, folder from the buttons of the toolbar.

 ![Toolbar buttons][5]

 Searching through tests is supported by a search field at the top right corner of the pane. The search text is dynamic and once typing starts, items will be filtered with every key stroke.

 ![Search][6]
 
 The Top right corner of the Project explorer pane is reserved for visibility controlling buttons. The pane can be docked, pinned or closed. In addition it can be moved by drag-drop of its header or resized by drag-drop of its borders.
 
 If the Project explorer pane is accidentally closed or in case a layout reset is needed, the View menu >> Reset Layout can be used.


## Disable Test Cases and Steps

Test cases and individual steps can be disabled. This way they remain part of the project, but will not be executed during test execution.

 ![Disable Step][7]


You can still execute a disabled test case or step if you explicitly select it and click on "Run Test" / "Run Step".


 [1]: /img/features/project-item-context-menu.png
 [2]: /img/features/folder-item-context-menu.png
 [3]: /img/features/test-item-context-menu.png
 [4]: /img/features/step-item-context-menu.png
 [5]: /img/features/project-explorer-create-buttons.png
 [6]: /img/features/project-explorer-search.png
 [7]: /img/features/disable-step.png
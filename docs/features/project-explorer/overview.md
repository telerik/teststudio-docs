---
title: Overview
page_title: Project Explorer Overview
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /features/test-maintenance/project-files-context-menu
publish: true
position: 1
---
# Project Explorer

The Project Explorer pane shows a tree-like structure of your tests in the project. Tests can be added directly to the project, or logically grouped in folders. Double click opens the test. Folders in turn, can be nested forming hierarchical representation of your testing solution. If there are multiple folders expanded you can collapse these using the Collapse button (available as of release R1 2018 - v.2018.1.0130).

![Collapse Button][4]

Each project file has a context menu with further actions that can be taken. Note that some context menu items will show up only for certain project file types.

## Project Context Menu Options

![Project Context Menu][1]

- **Add New Test** - create a new test within the project or folder.

- **Add New Code File** - add a new <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone code file</a>.

- **Add Existing Test** - add a previously created test to the project.

- **Add Existing Code File** - add an existing <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone code file</a>.

- **Create Folder** - add a new folder to the project.

- **Compile** - <a href="/features/coded-steps/compile-project" target="_blank">compile the project</a> excluding the tests set 'In Development'.

- **Connect to Source Control** - bind the project to TFS.

- **Rename** - edit the name of the project.

- **Close Project** - close the project.

- **Edit Embedded Api Project** - open the embedded Api project, applicable if there is an <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">Execute API Test as Step</a> in the project.

- **Open Project Folder in Windows Explorer** - launch an explorer window with the project path loaded.

## Test File Context Menu Options

![Test File Context Menu][2]

- **Open** - Open the selected test. You can also open a test by **double clicking** it.

- **Run Test** - execute the test.

- **Data Bind** - load the menu to bind the test to a data source.

- **Remove Data Binding** - remove link between the test and the data source it is currently bound to.

- **Used By** - Active for test used in Test as Step and shows a list of all test containing a reference to that one.

- **In Development/Remove In Development** - Active for web and wpf tests and indicates whether the test will be included in compilation. **Load and Manual tests could not be set 'In Development' mode.**

- **Exclude from Project** - remove the test or folder from the project, but keep it on disk.

- **Properties** - show all test properties.

## Folder File Context Menu Options

![Folder Context Menu][3]

The folder context menu options are a mix of the Project and Test context menus options.

> **In Development/Remove In Development** is also applicable for folders in Project Explorer providing both options. The option selected will be applied to all tests in the folder regardless their initial state.

## General Context Menu Options

- **Cut** - keyboard shortcut is Ctrl+X.

- **Copy** - keyboard shortcut is Ctrl+C.

- **Paste** - keyboard shortcut is Ctrl+V.

- **Delete** - permanently remove the file or folder from disk.

- **Rename** - edit the name of the test or folder.

[1]: /img/features/project-explorer/overview/fig1.png
[2]: /img/features/project-explorer/overview/fig2.png
[3]: /img/features/project-explorer/overview/fig3.png
[4]: /img/features/project-explorer/overview/collapse_button.png

---
title: Project Explorer Overview
page_title: Project Explorer Overview
description: "Project Explorer pane in Test Studio. The test explorer in Test Studio. Organize the tests structure in Test Studio project. Group few tests in a separate folder in Test Studio project. Project Explorer context menu in Test Studio"
position: 1
---
# Project Explorer

The **Project Explorer** pane shows a tree-like structure of your tests and folders in the project.

![Project Explorer][0]

Tests can be added directly to the project, or logically grouped in folders. Double click any test file to open it for editing. Folders in turn, can be nested forming hierarchical representation of your testing solution.

## Collapse Expanded Folders

If there are multiple folders expanded you can collapse these using the **Collapse** button.

![Collapse Button][4]

## Filtering Options in Project Explorer

To ease the navigation within the Project Explorer, Test Studio provides multiple options for filtering the existing tests - <a href="/features/project-explorer/search-tests" target="_blank">read further details</a> for the available options.

## Project Items Context Menu

Each project file has a context menu with further actions that can be taken. Note that some context menu options will show up only for certain project file types.

### Project Context Menu Options

![Project Context Menu][1]

- **Add New Test** - create a new test within the project or folder. A *'Create New Test dialog'* appears and allows you to choose the type of test and set its specific name.

- **Add New Code File** - add a new <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone code file</a>.

- **Add Existing Test...** - add a previously created test to the project. A *'Browse file dialog'* is opened and you can navigate to a Test Studio project and select the desired **.tstest* file.

- **Add Existing Code File...** - add an existing <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone code file</a>. A *'Browse file dialog'* is opened and you can navigate to a Test Studio project and select the desired **.cs* or **.vb* file.

- **Create Folder** - add a new folder to the project.

- **Import Project Settings** - you can reuse the Settings file of an already existing project. A *'Browse file dialog'* is opened and you can navigate to a Test Studio project root folder and select its *Settings.aiis* file.

- **Compile** - <a href="/features/coded-steps/compile-project" target="_blank">compile the project</a> excluding the <a href="/features/test-maintenance/tests-in-development" target="_blank">tests set 'In Development'</a>.

- **Connect to Source Control** - bind the project to <a href="/features/source-control/tfs/connect-to-tfs" target="_blank">TFS</a> or <a href="/features/source-control/git/connect-to-git" target="_blank">Git</a> remote repository.

- **Reconnect to Source Control** - (optional) if the project is connected to a source control repository and is currently disconnected, you can reconnect it.

- **Remove Source Control Binding** - (optional) if the project is connected to a source control repository and is currently disconnected, you can completely remove the Source Control Binding details for the current project.

- **Rename** - edit the name of the project.

- **Close Project** - close the project.

- **Edit Embedded Api Project** - open the embedded Api project, applicable if there is a nested <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">API Test as Step</a> in the project.

- **Open Project Folder in Windows Explorer** - launch an explorer window with the project root path loaded.

### Test File Context Menu Options

![Test File Context Menu][2]

- **Open** - Open the selected test. You can also open a test by **double clicking** it.

- **Run Test** - execute the test.

- **Data Bind** - load the menu to bind the test to a data source.

- **Remove Data Binding** - remove link between the test and the data source it is currently bound to.

- **Used By** - Active for test used in Test as Step and shows a list of all test containing a reference to that one.

- **In Development/Remove In Development** - Active for web and wpf tests and indicates whether the test will be included in compilation. **Load and Manual tests could not be set 'In Development' mode.**

- **Exclude from Project** - remove the test or folder from the project, but keep it on disk.

- **Show in Windows Explorer** - launch an explorer window with the test location path loaded.

- **Properties** - show all test properties.

### Folder File Context Menu Options

![Folder Context Menu][3]

The folder context menu options are a mix of the Project and Test context menus options.

> **In Development/Remove In Development** is also applicable for folders in Project Explorer providing both options. The option selected will be applied to all tests in the folder regardless their initial state.

### General Context Menu Options

- **Cut** - keyboard shortcut is Ctrl+X.

- **Copy** - keyboard shortcut is Ctrl+C.

- **Paste** - keyboard shortcut is Ctrl+V.

- **Delete** - permanently remove the file or folder from disk.

- **Rename** - edit the name of the test or folder.

[0]: /img/features/project-explorer/overview/fig0.png
[1]: /img/features/project-explorer/overview/fig1.png
[2]: /img/features/project-explorer/overview/fig2.png
[3]: /img/features/project-explorer/overview/fig3.png
[4]: /img/features/project-explorer/overview/collapse_button.png

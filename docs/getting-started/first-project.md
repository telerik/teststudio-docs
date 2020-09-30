---
title: Launch Test Studio
page_title: Launch Test Studio and Create Your First Project
description: "A step by step guide on what you can find in your first Test Studio project. Create a Test Studio Project. Start automating with Test Studio."
position: 1
---
# Create Your First Project

Once you have successfully <a href="/prerequisites/installation/install-procedure" target="_blank">installed</a> and <a href="/prerequisites/license-activation/activating-your-license" target="_blank">activated</a> Test Studio, and <a href="/prerequisites/configure-your-browser/browser-configuration" target="_blank">calibrated the browsers for test automation</a>, you are ready to create your first project and get familiar with the Test Studio layout. In this article you will find details about the following topics.

1. [Starting Welcome Screen](#starting-welcome-screen)
2. [Create Your First Project](#create-your-first-project)
3. [Test Studio Project Layout](#test-studio-project-layout)
4. [Types of Tests in Test Studio Project](#types-of-tests-in-test-studio-project)
5. [Types of Files in Test Studio Project](#types-of-files-in-test-studio-project)
6. [Elements in Test Studio Project](#elements-in-test-studio-project)

<br><br>
<div><a style="float:right" href="/getting-started/first-test">Go to <strong>Your First Test</strong></a></div>
<br><br>

## Starting Welcome Screen

Launching Test Studio will get you to the [**Welcome Screen**](/general-information/start-a-project/welcome-screen). It lets you create new or open existing projects, access demo resources, see notifications about software updates and news related to the product.

![Launch Test Studio Welcome Screen](/img/getting-started/first-project/fig0a.png)

## Create Your First Project

In the [**Project**](/general-information/start-a-project/welcome-screen#create-a-new-project) section you can decide whether to create a new project, open a local one, choose from the recently used or open a source controlled project (Git or TFS).Let's create a new project for the current demonstration, specify its name and location and click the **Create** button.

![Create new Project](/img/getting-started/first-project/fig00.png)

You can explore a sample **Web & Desktop** project, from the [**Get Started**](/general-information/start-a-project/welcome-screen#get-started) section.

![Get Started Projects](/img/getting-started/first-project/fig01.png)

## Test Studio Project Layout

Creating a new Test Studio project launches the default project layout. This consists of useful panels providing plenty of useful components. To help you speed up your flawless work with Test Studio, you can refer the below notes for each of these.

- <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a> - this is the pane, which displays the structure of the project with all tests, coded files, folders in the project root folder. Provides access to the items properties, allows you to copy, cut and paste these, add new items, etc.
- <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a> - this is the pane, which shows all elements referred from the test steps in the project, structured in a tree view, which includes page node, frame, element. Provides access to the elements' find expressions and properties, allows you to edit these.
- <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a> - this is the pane, which shows the selected component (test, element, coded file) and allows you to edit it.
- <a href="/features/coded-steps/output-panel" target="_blank">__Output Pane__</a> - this is the pane, which displays different messages related to your work in the project - syntax or compilation errors when adding code snippets, or messages in regards the Source Control related actions.
- <a href="/general-information/test-recording/step-suggestions" target="_blank">__Step Builder__</a> - this is the pane, which allows you to add different steps in the tests even if no recording session is currently active.
- __Properties Pane__ - this is the pane to list the properties of the currently selected item (test, step, element, page node, frame) and allows you to edit these.
- __Tools Ribbon__ - the Tools Ribbon provides access to various settings in regards the active tab in the project.

![Project Layout](/img/getting-started/first-project/project-components.png)

> After the project is successfully created, you can open the <a href="/general-information/start-a-project/in-product-tips-tricks" target="_blank">Tips and Tricks</a> from the top right corner of Test Studio. The popup dialog has many useful references to the documentation and a short video on some of the topics.

## Types of Tests in Test Studio Project

One Test Studio project allows you to include different types of tests:

- __Web Test__ - a test in which you can record actions against a web page started in any of the supported browsers (Chrome, Firefox, Edge, IE).
- __WPF Test__ - a test in which you can record actions against a WPF desktop application.
- __Load Test__ - a test in which you can add different scenarios with web requests to load a web application server.
- __Manual Test__ - a test in which you can add steps to manually execute against any application. This can be converted to a web test if automating a web page.
- __Performance Test__ - a Performance test is always related to a valid web test and is being executed on top of this.

<table id=no-table>
	<tr>
		<td>![Add new Test from Ribbon](/img/getting-started/first-project/add-new-test1.png) <td>
		<td>![Add new Test from Project root](/img/getting-started/first-project/add-new-test2.png)</td>
	</tr>
<table>

## Types of Files in Test Studio Project

The files displayed in the __Test Studio Project Explorer__ are the different tests files, the code files - a standalone class file, or a code-behind file related to a web or WPF test, which combines recorded and coded steps. All these can be organized in folders.

![File Types in the Project](/img/getting-started/first-project/file-types.png)

If you browse the project root folder in the __Windows File Explorer__, you can see some additional folders and files, which are not listed in the __Test Studio Project Explorer__. Here is what these are related to:

- __ApiTests__ - the folder, which stores the embedded API testing project, if there is such.
- __Data__ - the folder, which stores all external data source files, added in the project for data driven testing.
- __myProjectFolder__ - the folder created in the Test Studio Project Explorer and which contains other tests, and/or code files.
- __Results__ - the folder, which stores the generated results from local test list execution.
- __TestLists__ - the folder, which stores the test lists files.
- __*.imgstore__ - the resource file, which stores information for the elements' images, recorded in the respective test.
- __*.resx__ - the resource file, which stores information for the story board iamges for the respective test.
- __*.tstest__ - the test file.
- __*.tstest.cs (or *.tstest.vb)__ - the code-behind file, related to the respective web or WPF test, which combines recorded and coded steps. 
- __*.cs (or *.vb)__ - the standalone class file, which can contain any custom code.
- __Pages.g.cs (Pages.g.vb)__ - the file, which stores all recorded elements in the web and WPF tests in the project.
- __Settings.aiis__ - the file, which stores the project settings.

![File Types in the Project in FIle Explorer](/img/getting-started/first-project/file-types-in-file-explorer.png)

## Elements in Test Studio Project

The <a href="/features/elements-explorer/overview" target="_blank">__Test Studio Elements Explorer__</a> provides the visual representation of all elements recorded or manually added during the Test Recording process and allows you to edit the way they are found during execution. The elements are organized under Page nodes (and also Frame nodes if there are frames used in the web page) for web applications and Application and Window Caption nodes for WPF applications.

![Elements in the Test Studio Elements Explorer](/img/getting-started/first-project/elements-and-page-nodes.png)

<div><a style="float:right" href="/getting-started/first-test">Go to <strong>Your First Test</strong></a></div>
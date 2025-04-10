---
title: Welcome Screen
page_title: Welcome Screen
description: "Test Studio welcome screen. Start a new project in Test Studio. Open an existing project in Test Studio. Get started with Test Studio. Update Test Studio. Check/Find Test Studio version. News related to Test Studio. New Test Studio blogs"
position: 0
---
# Welcome Screen

Once you successfully <a href="/prerequisites/license-activation/activating-your-license" target="_blank">activate a Test Studio license</a> and launch the app, it takes you to the **Welcome Screen**. In this view you can create or open an existing project and access useful samples and tutorials resources.

This article guides you through the different tabs of the **Welcome Screen**:

- [Welcome Screen](#welcome-screen)
  - [Project Section](#project-section)
    - [Create a New Project](#create-a-new-project)
    - [Open an Existing Project](#open-an-existing-project)
    - [Open Source Control](#open-source-control)
  - [Get Started Section](#get-started-section)
  - [News Feed Section](#news-feed-section)

## Project Section

In the __Project__ section of the __Welcome screen__, you can choose between creating a [new project](#create-a-new-project) or [opening an existing one](#open-an-existing-project). You can pick from a list of recently used projects on the left, or browse your local folders through the __Open Local__ button. You can also [open a remote project from a source control repository](#open-source-control) (Git or TFS).

![Project Section](/img/getting-started/first-project/fig0a.png)

> __Tip__
><br>
><br>
> Once you open the test project, you can <a href ="/automated-tests/customize-project/custom-layout" target="_blank">adjust the Test Studio layout</a> and make it fit your environment and needs.

### Create a New Project

To create a new project you can choose between a couple types of testing 
- __Web Testing__, 
- __Desktop Testing__,
- __WPF Testing__, or 
- __Load Testing__ (Load testing is only available in Test Studio Ultimate). 

Depending on your choice the newly created project contains a test of the selected type. The initial test type selected in the beginning does not limit the project to only this type of tests. Any Test Studio test can be added at any time in the project.

![Project Type](/img/automated-tests/customize-project/welcome-screen/fig01.png)

To create a new project:

1. Choose the type of testing to start with.

2. Set the project name and, optionally, change the location folder where Test Studio projects are stored.

3. Confirm the creation with pressing the __OK__ button. The __Cancel__ button returns you to the previous screen.

![Create new Project](/img/getting-started/first-project/fig00.png)

The default location where Test Studio creates projects is __C:\Users\\\<yourUsername>\Documents\Test Studio Projects__. The __Browse Folder__ button allows you to change this location by choosing another folder.

> __Note__
><br>
><br>
> The __user needs to have read/write permissions for the folder__ in which the project is created. 

### Open an Existing Project

The **Recent projects** section on the left shows a list of the projects you worked on lately - these are listed with their name and folder location. The _Delete_ icon removes the project from the list (it does not remove the actual project files from the disc). 

The __Open Local Project__ option let's you browse to a local folder which contains a Test Studio project to load.

![Open Existing Project][4]

> __Note__
><br>
><br>
> The __user needs to have read/write permissions for the folder__ in which the existing projects are stored.

### Open Source Control

Test Studio provides built-in integration for TFVC and Git based repositories. The __Open Source Control__ option let's you specify a remote repository to clone locally - you can choose from <a href ="/automated-tests/source-control/git/open-git-project" target="_blank">Git</a> or <a href ="/automated-tests/source-control/tfs/open-tfs-project" target="_blank">TFS</a>.

> __Note__
><br>
><br>
> The __user needs to have read/write permissions for the folder__ in which the project gets cloned.

## Get Started Section

The __Get Started__ section lets you create the demo project, open the online help documentation and public Telerik forums, and submit your feedback or tickets to the Support team.

![Get Started][5]

## News Feed Section

The __News Feed__ section lists important news related to the product, links to new Test Studio blog posts on the Telerik site. The content is updated live and requires Internet connection.

![Newsfeed][7]




[4]: /img/automated-tests/customize-project/welcome-screen/fig4.png
[5]: /img/automated-tests/customize-project/welcome-screen/fig5.png

[7]: /img/automated-tests/customize-project/welcome-screen/fig7.png

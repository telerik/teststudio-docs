---
title: Script Project Settings
page_title: Script Project Settings
description: "Test Studio script coded code settings. Where is the Namespace in Test Studio project How to add reference/reference assembly in a Test Studio project.  Test Studio project's bin folder "
position: 7
---
# Script Project Settings

Script Options dictate how Test Studio treats the <a href="/advanced-topics/coded-steps/code-behind-file" target="_blank">code behind file</a>. Note: This section is applicable to the Standalone version only.

![Script Options][1]

## Assembly Name

Defaults to the name of the project.

## Output Folder

Alter the name of the folder within your project folder that holds the project's DLL and PDB files. The default is "bin".

## Namespace

Defaults to the name of the project.

## Code Base Class

This option allows you to create and use a specialized test class. For example, you could create a class that knows how to log to your corporation's database. The code-behind for a Test Studio test uses "BaseWebAiiTest" by default. BaseWebAiiTest is an object that knows how to execute test steps, find elements on a page, perform actions against all browser types (i.e. click, scroll, etc) and log test results. BaseWebAiiTest also keeps track of the active browser and the test data.

## Project References

Here you can see a list of existing project references, add a new reference, or delete an existing one. Please see our user's guide on <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">How to Add an Assembly Reference</a> for more information.

## Reset References

Click this button to restore the default references.

[1]: /img/features/project-settings/script-options/fig1.png
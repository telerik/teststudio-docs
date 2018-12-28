---
title: Coded Steps
page_title: Coded Steps
description: "Progress® Test Studio® for APIs - Code Features - Coded Steps"
position: 1
publish: true
---

# Coded Steps

Coded steps in Progress® Test Studio® for APIs can be used to execute C# or Visual Basic code as part of the test execution. Each coded step points to and executes a method in its test case's code-behind file. Use a coded step for a scenario that requires more complexity than what can be achieved with the functionality of the rest of the provided [step types](../steps/Overview).

## Add New Coded Step

A coded step can be added to a test case using the Add Step menu in the test's context menu in the project explorer

![Create Coded Step from Project Explorer][1]

or using the Add a Step button in the test explorer.

![Create Coded Step from Test Explorer][2]

## Select Project Language

If this is the first time you are adding a coded step to this project, you will be prompted to select a [coding language for the project](./project-coding-language) (C# or Visual Basic).

## Create Code-Behind File

Adding a coded step to a test case will create a code-behind file, associated to that test. You can also choose to manually create the code-behind file before creating any steps. To do that, use the "**Add Code-Behind**" option in the test's context menu in the project explorer.

![Add Code-Behind File][3]

Next to each test case that has a code-behind file, you will sea a button in the project explorer, that can be used to open the code-behind file.

![Open Code-Behind][4]

Once created, the test's code-behind file cannot be deleted from the UI. If you wish to remove it, you should create a new test case, move your non-coded steps there and delete the old test case (which will delete its code-behind file too).

## Map Coded Step to a Code-Behind Method

When a new coded step is created, you need to select the method that should be executed when the step is run. You can choose between any already existing public method in the test's code-behind file or click on `<New Test Method>` which will create a new method for you.

![Select Test Method][5]

Note that if you later rename the method in the code-behind file, that will break the coded step mapping. Once a method name is changed, you need to open any coded step that used to point to it and remap it to the new method name or another existing method. A warning indicator in the project explorer will guide you whenever there is a broken or missing coded-step-to-method reference as shown in the following images.

![Invalid Method Mapping][6]

![Select Valid Test Method][7]

## Coded Step Contition

Coded steps can have a [condition](../condition). Use it whenever you wish to skip the step's execution based on a chosen criteria.


## See Also

* [Code-Behind Files](./code-behind-files)
* [Standalone Code Items](./code-items)
* [Project Code Language](./project-coding-language)
* [Compile Project](./compile-project)
* [Debug Project](./debug-project)
* [Output Panel](./output-panel)
* [Add Assembly Reference](./add-assembly-reference)


[1]: /img/features/code-features/add-coded-step-context-menu.png
[2]: /img/features/code-features/add-coded-step-test-explorer.png
[3]: /img/features/code-features/add-code-behind.png
[4]: /img/features/code-features/open-code-behind.png
[5]: /img/features/code-features/coded-step-select-method.png
[6]: /img/features/code-features/invalid-method-mapping-warning.png
[7]: /img/features/code-features/coded-step-select-valid-method.png

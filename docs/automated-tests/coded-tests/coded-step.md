---
title: Introduction to Coded Tests
page_title: Coding Options In Test Studio Test
description: " What coding options there are in Test Studio. What coding language can I use in Test Studio project/ Create Coded Step in Test Studio test. How to create coded test in Test Studio. Implement custom coded actions in Test Studio test. Helper Utility class file in Test Studio project. "
position: 0
---
# Introduction to Coded Tests

Test Studio allows you to combine the recorded actions in a test with coded solutions for any specific and complex scenarios, which require customization beyond the built-in verifications and actions capabilities.

In this article you can find the important topics about coding in Test Studio project:

- [What language can I use to write code in Test Studio tests?](#what-coding-language-can-be-used-in-test-studio-project)
- [Can I use the recorded steps in code?](#convert-a-recorded-step-to-coded-function)
- [How to create an empty coded function in the test?](#insert-empty-coded-step)
- [How to create a code item accessible for all tests in the project?](#which-is-the-standalone-code-file)
- [Can I search in the code file?](#code-editor-options)

## What Coding Language Can Be Used in Test Studio Project?

Test Studio supports two types of coding languages - __C#__ and __VisualBasic__. The language is set on project level when adding the first coded item.

![Choose coding language][1]

> __Tip__
><br>
><br>
> Once the scripting language is set on project level, it __cannot be changed__ to the other option. If you need to transform the coded solution to the other language, you need to __manually convert the code___ to the other scripting language.

## How to Implement a Coded Function in the Test?

In Test Studio tests you can take advantage of reusing the recorded steps as coded functions as well as adding your own custom coded logic.

### Convert a Recorded Step to Coded Function

Most of the recorded steps can be converted to their corresponding coded function and allows to further customize the tests and actions. Select a recorded step, right click on it to trigger the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> and choose the option __Edit in Code__.

![Convert to code][4]

This automatically converts the step into a coded one and creates a new test method in the coded file associated with the test. The method represents the code required for this step depending on its type and different settings and properties set.

![Recorded step in code][5]

> __Tip__
><br>
><br>
> Check out <a href="https://www.telerik.com/blogs/writing-coded-steps-test-studio" target="_blank">this neat tutorial</a> on converting steps to coded functions in Test Studio.

### Insert Empty Coded Step

To insert an empty coded step in the test choose the 'Coded Step' option from the <a href="/features/custom-steps/overview" target="_blank">Step Builder</a> - it is listed under the __Common__ section.

![Add a coded step][2]

Adding the first coded step in a test automatically creates a coded file associated with the test. Test Studio switches from the test to the code file and allows writing the custom coded function in the empty test method.

![First coded step][2g]

The automatically generated coded file contains some predefined values like the necessary `using` (or `Import`) statements, the project `namespace` and the base test class `BaseWebAiiTest` inherited from the current test class. All these options are customizable and can be maintained on project level in the <a href="/features/project-settings/script-options" target="_blank">Project Settings -> Script tab</a>.

![Usings, namespace, base test][10]

> __Note__
><br>
><br>
> The `namespace` in all coded items should be the same. Otherwise the project cannot be compiled and the tests cannot be executed.
><br>
><br>
> Any <a href="/automated-tests/coded-tests/add-assembly-reference" target="_blank">external dll referenced</a> in the Test Studio project should be included as `using` (or `Import`) statement in the code file where it will be used.

For this example I will add a simple statement to refresh the page DOM tree - the test method in which the code is added is _public void demoTest_CodedStep()_.

![Custom code added][11]

Switching back to the test steps, shows that the test method is selected for the coded step and thus can be executed as part of this test.

![Coded step added in test][12]

### Add Next Coded Step in the Test

_What if you need to insert another coded step in the same test?_

Test Studio gives the option to reuse the already existing test method, or to create a new one and insert different coded function.

![Second Coded step added in test][12g]

Each coded step in the test needs to be mapped to a method from the coded file. You can choose from the coded step dropdown to map it to any of the already existing test methods, or select the option to define a new one.

![Map coded step][3]

> __Tip__
><br>
><br>
> Multiple coded steps in the same test can be mapped to a single method in the test coded file.

## Which is the Code-Behind File?

The code-behind file is the one created with the first coded step in a test. It is associated with that test and can be used in another project if moved with the test.

> __Tip__
><br>
><br>
> When moving a test to another project, it is recommended to use the option to <a href="/knowledge-base/best-practices-kb/add-existing-test" target="_blank">add an existing test</a>).

## Which is the Standalone Code FIle?

Test Studio allows adding a code file on project level and it is usually called _standalone code file_. It can be used to create a utility class that defines a set of methods to perform common, often re-used functions. The code item can be used also as a helper class to assist in providing some extended functionality for your test project.

To insert a standalone code file use the option 'Add New Code File' from the <a href="/features/project-explorer/overview#project-items-context-menu" target="_blank">context menu</a> in the Project Explorer. You can add the coded file on project root level, or in any sub-folder.

![Standalone Code file][13]

> __Tip__
><br>
><br>
> <a href="/advanced-topics/coded-samples/general/utility-class-in-standalone" target="_blank">Here</a> you can find an example of a utility class file and how to use it from the tests in the project.

## Code Editor Options

All coded files in Test Studio project are opened in the code editor. It provides __Quick Find__ and __Quick Replace__ features to ease navigation and maintenance of the custom code. You can open it from the _Find_ icon in the top bar, or standard _Ctrl+F_ shortcut.

The search and replace functionality works in the file which is currently active.

![Code Editor][5a]

There is a context menu in the coded editor, which allows you to comment or uncomment multiple lines of code when selected. You can also use the keyboard shortcuts _Ctrl+K_ (comment) and _Ctrl+U_ (uncomment).

![Context Menu][6a]

[1]: /img/features/coded-steps/coded-steps/fig1.png
[2]: /img/features/coded-steps/coded-steps/fig2.png
[2g]: /img/features/coded-steps/coded-steps/add-coded-step.gif
[3]: /img/features/coded-steps/coded-steps/fig3.png
[4]: /img/features/coded-steps/coded-steps/fig4.png
[5]: /img/features/coded-steps/coded-steps/fig5.png
[10]: /img/features/coded-steps/coded-steps/fig10.png
[11]: /img/features/coded-steps/coded-steps/fig11.png
[12]: /img/features/coded-steps/coded-steps/fig12.png
[12g]: /img/features/coded-steps/coded-steps/add-second-coded-step.gif
[13]: /img/features/coded-steps/standalone-code-file/fig1.png 
[5a]: /img/features/coded-steps/code-behind-file/fig5.png
[6a]: /img/features/coded-steps/code-behind-file/fig6.png
---
title: Compile Project
page_title: Compile Project with Coded Files
description: "Compile Project with coded steps or files in Test Studio. Verify if inserted custom code can be compiled. Resolve compilation errors"
position: 3
---
# Compile Project with Coded Files

Adding custom code into the test project requires its compilation before test execution. That way you can identify any compile-time errors such as incorrect syntax, misspelled keywords, type mismatches, and incorrect method binding. Test Studio allows you to compile the project while setting up the code functions.

The __Compile__ button is listed under the _Project_ ribbon, or in the _Project Explorer_ <a href="/features/project-explorer/overview#project-items-context-menu" target="_blank">context menu</a> on project level.

![New Compile button][1]

The options __Compile__ and __Compile All__ are related to the feature to mark a test or code file with <a href="/features/test-maintenance/tests-in-development" target="_blank">*'In development'*</a> flag. That way you can keep some _work in progress_ coded files, which are not yet set up completely, and continue running tests from the project.

* __Compile__ - exclude the 'InDevelopment' files from compilation.
* __Compile All__ - compiles all files in the project.

## Compilation Output

The output of the compilation process is displayed in the <a href="/features/coded-steps/output-panel" target="_blank">**Output Panel**</a> under the Compiler tab. Any errors detected will be listed there.

![Output panel][2]

[1]: /img/features/coded-steps/compile-project/fig1.png
[2]: /img/features/coded-steps/compile-project/fig2.png
[3]: /img/features/coded-steps/compile-project/fig3.png
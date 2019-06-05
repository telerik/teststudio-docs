---
title: Compile Project
page_title: Compile Project
description: "Compile Project with coded steps files in Test Studio."
position: 3
---
# Compile Project

## Version 2017 R3 and later

As of version 2017 R3 you have the ability to mark tests and standalone code files with <a href="/features/test-maintenance/tests-in-development" target="_blank">**'In development'**</a> flag to exclude these from compilation. Thus the **Compile button** is extended and you could choose whether to **'Compile All'** files or **'Compile'** only these **not marked** as 'In development'. 

The default action set in the <a href="/features/project-explorer/overview" target="_blank">Project context menu</a> and for the Compile button is 'Compile'.

![New Compile button][1]

By compiling the test project you can identify compile-time errors, such as incorrect syntax, misspelled keywords, type mismatches, and incorrect method binding.

When you compile the test project Test Studio builds the project dll in the **bin** folder of the project.

The output of the compilation process is displayed in the <a href="/features/coded-steps/output-panel" target="_blank">**Output Panel**</a> under the Compiler tab.

![Output panel][2]

## Version 2017 R2 and earlier 

Press the **Compile** button in the ribbon to compile the entire test project.

![Compile button][3]

[1]: /img/features/coded-steps/compile-project/fig1.png
[2]: /img/features/coded-steps/compile-project/fig2.png
[3]: /img/features/coded-steps/compile-project/fig3.png
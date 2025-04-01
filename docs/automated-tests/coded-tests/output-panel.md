---
title: Output Panel
page_title: Output Panel
description: "Output Panel in Test Studio project. "
position: 4
---
# Output Panel

The Output panel displays a record of log messages recorded by Test Studio throughout runtime. These include build errors that occur when a <a href="/features/coded-steps/compile-project" target="_blank">project is compiled</a>.

Its default location is in the middle bottom pane.

![Output panel][1]

## Tabs In The Output Panel

You could chose between **Syntax Errors**, **Compiler** and **Source Control** tab to filter the type of information in the panel.

Under the **Syntax Errors** tab can be found the syntax errors throughout runtime. These errors are designed to indicate important events and help pinpoint where problems may occur.

![Errors tab][2]

Under the **Compiler** tab can be found information (if you have a code-behind file) about a specific error message or warning during the compilation of the project.

![Compiler tab][3]

Double-click any error message entry will navigate to the file where the problem occurs, and move to the error location.

Under the **Source Control** tab can be found information about the actions taken against the Source control (connect, check in, check out). 

![Source Control][4]

[1]: /img/features/coded-steps/output-panel/fig1.png
[2]: /img/features/coded-steps/output-panel/fig2.png
[3]: /img/features/coded-steps/output-panel/fig3.png
[4]: /img/features/coded-steps/output-panel/fig4.png

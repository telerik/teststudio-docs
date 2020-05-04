---
title: Code-Behind File
page_title: Code-Behind File
description: "Code-Behind File of a test in Test Studio."
position: 1
---
# Code-Behind File #

## Standalone version ##

You can create a code behind file for each test where you can implement <a href="/features/coded-steps/coded-step" target="_blank">coded steps</a> and custom test classes.

There are two methods of creating a code behind file for your test.

1.&nbsp;  Add a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a> from the Step Builder.

2.&nbsp; Right click on a step and select Edit in Code from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">Test Step Context Menu</a>.

![Code-behind file][1].

* Every method in the code-behind file is represented in the <a href="/features/coded-steps/coded-step" target="_blank">coded step drop down</a> .

* Every coded step can be mapped to any method in the code-behind file. 

* Do not remove the *CodedStep* attribute. This is how Test Studio recognizes custom coded steps versus other methods it should ignore.

* The code-behind file has access to all Telerik run-time objects, like *ActiveBrowser*. This is an identical coding experience to the <a href="/testing-framework/getting-started" target="_blank">Telerik Testing Framework</a>.

## Visual Studio plugin ##

There are three ways how to add a code-behind file in Visual Studio plugin.

1.&nbsp; Click **Add code-behind file to your test** button

![Add Code Behind File][3]

2.&nbsp; Add a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a> from the Step Builder.

3.&nbsp; Right click on a step and select Edit in Code from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">Test Step Context Menu</a>.

The code-behind file is nested under the parent test in Solution Explorer:

![Code Behind File][4]

## Code Editor in Standalone Version ##

The code editor in version 2019 R3 and later has a Quick Find and Quick Replace features to make it easier to navigate and maintain your code. You can open it from the Find icon in the top bar, or standard CTRL+F and CTRL+R shortcuts. 

The search and replace functionality is against the file that is currently open.

![Code Editor][5]

The code editor has a context menu with more actions. You can comment or uncomment your code from the context menu or with CTRL+K and CTRL+U shortcuts respectively.

![Context Menu][6]

**See Also:**

*	<a href="/features/coded-steps/coded-step" target="_blank">Coded Step</a>

[1]: /img/features/coded-steps/code-behind-file/fig1.png
[2]: /img/advanced-topics/coded-steps/code-behind-file/fig2.png
[3]: /img/advanced-topics/coded-steps/code-behind-file/fig3.png
[4]: /img/features/coded-steps/code-behind-file/fig4.png
[5]: /img/features/coded-steps/code-behind-file/fig5.png
[6]: /img/features/coded-steps/code-behind-file/fig6.png
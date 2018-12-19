---
title: Coded Step
page_title: Coded Step
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Coded Step

This function adds a coded step, opens the code editor, and allows you to input custom code. This is for more complicated steps that cannot be recorded through the user interface. Visit the <a href="/features/coded-steps/coded-step" target="_blank">Coded Steps section</a> for more details.

In the Standalone version, write your code in the white area under Routine and Description. Note that the coded step is named after the test and you can input a custom description. If you receive an Assembly Reference error upon execution, please see our article on how to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> in the standalone version.

As of version 2015 R1 you can find the custom steps in the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a> under General section.

![Add coded step][2]

In the VS plugin, you are taken to the code behind file where you can insert your custom code. If you receive a Deployment error upon build/rebuild, please read this <a href="/troubleshooting-guide/visual-studio-tg/enable-deployment" target="_blank">KB article</a> for a solution.

![In VS](/img/features/custom-steps/script-step/fig2.png)


[2]: /img/features/coded-steps/coded-steps/fig2.png

**See Also:**

*	<a href="/features/coded-steps/coded-step" target="_blank">How to use coded step</a>
---
title: Coded Step
page_title: Coded Step
description: "How can I execute some code at certain point of the test execution in Test Studio. Can I combine the recorded steps with some coded solution in Test Studio test."
position: 3
---
# Coded Step

This function adds a coded step, opens the code editor, and allows you to input custom code. This is for more complicated steps that cannot be recorded through the user interface. Visit the <a href="/features/coded-steps/coded-step" target="_blank">Coded Steps section</a> for more details.

Write your code within the method defined in the coded file. Note that the coded step is named after the test and step and you can input a custom description.

![Add coded step][2]

If you receive an Assembly Reference error upon execution, please see our article on how to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> in the standalone version.

In the VS plugin, you are taken to the code behind file where you can insert your custom code. If you receive a Deployment error upon build/rebuild, please read this <a href="/troubleshooting-guide/visual-studio-tg/enable-deployment" target="_blank">KB article</a> for a solution.

![In VS](/img/features/custom-steps/script-step/fig2.png)

[2]: /img/features/coded-steps/coded-steps/fig2.png

---
title: Coded Step
page_title: Create Coded Step
description: "Create Coded Step in Test Studio test."
previous_url: /user-guide/coded_steps.aspx, /user-guide/coded_steps, /advanced-topics/coded-steps/coded-step 
position: 0
---
# Create Coded Step

## Standalone

<a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> supports coded steps. This allows you to write code and have it executed as a test step. Use a coded step for a scenario that requires more complexity than what can be composed with the Verification Builder or by actions from the Elements Menu. 

1.&nbsp; Add a coded step from the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a> under Common section.

![Add a coded step][2]

2.&nbsp; Select the codding language.

![Codding language][1]

This creates a <a href="/features/coded-steps/code-behind-file" target="_blank">code-behind file</a> with an empty test method where you can implement your custom code.

3.&nbsp; In order to execute the code in the test method you should bind it to an existing coded step in the test. All valid methods are presented in the coded step drop down menu. Select one and save the test.

![Map coded step][3]

> Many coded steps can be mapped to a single method.

4.&nbsp; You can add a new method by clicking **New Coded Function** from the drop down.

![New coded function][4]

[1]: /img/features/coded-steps/coded-steps/fig1.png
[2]: /img/features/coded-steps/coded-steps/fig2.png
[3]: /img/features/coded-steps/coded-steps/fig3.png
[4]: /img/features/coded-steps/coded-steps/fig4.png



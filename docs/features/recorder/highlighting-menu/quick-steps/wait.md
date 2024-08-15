---
title: Add Wait Step
page_title: Add Wait Step
description: "Test Studio provides interactive suggestions for adding wait steps during recording based on the highlighted element. Wait steps are useful for holding the test exexution until an element is in incertain state. Use one click to add wait step in Test Studio test. The wait steps helps in synchronizing the test execution depending on how fast the automated application loads the elements."
position: 2
---
# Wait Steps

Wait steps in Test Studio allow you to design your automation tests in a stable and reliable manner. With the wait steps you can ensure that each next action won't get executed before the element doesn't exist or is not yet visible.

Find out more about waits steps and how to record these in the below article.

- [General notes about wait steps](#general-notes)
- [Add a wait step](#create-a-wait-step-in-recording-mode)
- [Add a wait step without recording session](#create-a-wait-step-without-recording-session)

## General Notes

The Test Studio wait steps are using the implementation for verification steps. But instead of passing or failing based on a comparison, the wait step waits until the comparison is true. It fails when the step wait timeout is over and the comparison is still not fulfilled.

> **Note**
>
> The engine for creating the verification sentences allows you to __convert any Verification step to Wait or Extraction step (converting to extraction step is available for text based verification)__. Use the _Change Role_ option from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> and choose from the options in the sub-menu.
> ![Change Role Option](/img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/fig0.png)

## Create a Wait Step in Recording Mode

The <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">Highlighting menu</a> gives quick access to a set of predefined waits, which can be added with a single click while recording. You can follow the below steps to insert a wait step in your test.

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio official page</a>.

2.&nbsp; Enable the highlighting once the recorder is attached to the browser. Hold the mouse over the __Download Free Trial__ button and add a wait step for the element to be visible. Then record the click on the button.

![Add wait step][1]

3.&nbsp; Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the wait step and allow you change the interval of checking the expected state and the overall timeout to wait for.

![Step Properties][3]

## Create a Wait Step without Recording Session

The automated test execution is much faster than a real user and often you find out it is suitable to __add an additional wait in the already recorded test__ to ensure its stability. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional wait steps.

For the cases when the project and scenarios are quite complex, you can __add waits for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.
</br>
</br>
__Note:__  Usually, the wait step to insert is related to an action step and its element. Thus, if you click on that action step, its target element gets highlighted in the Elements Explorer with a red arrow. Select the element and proceed to the Step Builder.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the wait type you need and click the **Add Step** button to insert the step in the test.

![Step Builder Verification][4]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

## See Also

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick verification</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced verification</a>

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/add-wait-step.gif
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig4.png


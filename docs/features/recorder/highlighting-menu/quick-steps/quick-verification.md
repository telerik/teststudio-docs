---
title: Add Verification Step
page_title: Add Verification Step
description: "Test Studio provides quick verification suggestions during recording based on the highlighted element. Verifications are useful for asserting the state of element in the tested application. Use one click to add verification in Test Studio test."
position: 1
---
# Verification Steps

Verification steps in Test Studio allow you to design your automation tests in a stable and reliable manner. With the right verification step you can ensure the state of the application at each action.

Find out more about verification steps and how to record these in the below article.

- [General notes about verifications](#general-notes)
- [Add a quick verification](#create-a-verification-step-in-recording-mode)
- [Add a quick verification without recording](#create-a-verification-step-without-recording-session)

## General Notes

While recording the automated test scenarios you visually validate that each of your actions is accepted and processed from the tested application. The __verification steps let you create any sort of checks for an element__. That way you can ensure what is the state of that element during the test run and if it is what you expect before and after performing an action against it.

> **Tip**
>
> Take a look <a href="https://www.telerik.com/blogs/make-your-automated-tests-see-better-than-yourself" target="_blank">at this blog post about using verification and wait steps</a> in the automation tests.

The verification steps in Test Studio allows you to:

- Use multiple checks against different criteria at one time.
- Build these checks out-of-the-box in an interactive manner during recording the test scenarios without using code.
- Detect if elements are in a particular state (e.g. is visible, exists).
- Detect if attributes and properties compare with specific values.
- Verify content, attributes, images, image texts, styles, visibility, drop-down list selections, checkboxes, radio buttons, tables and etc.

> **Tip**
> <br>
> Check out this <a href="https://www.youtube.com/watch?v=Klt3fRglAeU&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=3" target="_blank">getting started video</a> about wait and verification steps in Test Studio.

Test Studio implements verification through "sentences" that compare a portion of an element to a value, such as:

- textbox content is equal to 'order 2011'
- image path contains 'http://www.telerik.com'
- wait for element to exist

> **Note**
>
> The engine for creating the verification sentences allows you to __convert any Verification step to Wait or Extracttion step (converting to extraction step is available for text based verifications)__. Use the _Change Role_ option from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> and choose from the options in the sub-menu.
> ![Change Role Option](/img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/fig0.png)

## Create a Verification Step in Recording Mode

The <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">Highlighting menu</a> gives quick access to a set of predefined verifications, which can be added with a single click while recording. You can follow the below steps to insert a quick verification step in your test.

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio official page</a>.

2.&nbsp; This sample scenario clicks on the __Download Free Trial__ button and enables highlighting on the next page. Hold the mouse over the title and add a verification for its text content to ensure the correct product download is triggered.

![Add quick verification][1]

## Create a Verification Step without Recording Session

The automated test execution is much faster than a real user and often you find out it is suitable to __add an additional wait in the already recorded test__ to ensure its stability when running on different environments. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional waits.

For the cases when the project and scenarios are quite complex, you can __add wait steps for an already recorded element__ and without starting a recording session.

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.
</br>
</br>
__Note:__  Usually, the wait step to insert is related to an action step and its element. Thus, if you click on that action step, its target element gets highlighted in the Elements Explorer with a red arrow. Select the element and proceed to the Step Builder.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the verification you need and click the **Add Step** button to insert the step in the test.

![Step Builder Verification][2]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

## See Also

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced verification</a>

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/add-quick-verification.gif
[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/fig2.png

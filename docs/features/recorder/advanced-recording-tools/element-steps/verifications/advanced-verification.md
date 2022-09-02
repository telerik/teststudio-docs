---
title: Advanced Verification
page_title: Build Advanced Verifications
description: "Test Studio allows you to create Advanced Verifications for all element attributes, styles, etc. Insert verifications specifically build for an element from the tested application. "
position: 1
---
# Advanced Verifications

The __Advanced Verification Builder__ allows you to interactively build custom verification rules and validate them against the tested application in live recording session.

Find out more about the available verifications in Test Studio. 

## Create an Advanced Verification

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/teststudio" target="_blank">Telerik Test Studio official page</a>.

2.&nbsp; This sample scenario clicks on the __Download Free Trial__ button and enables highlighting on the next page. Hold the mouse over the title to highlight the element and choose the option to <a href="/automated-tests/recording/hover-over-highlighting#build-step" target="_blank">Build Step...</a>. Open the **Verifications** section under the Elements Steps tab

![Verifications section in Elements Steps][2]

2.&nbsp; You can choose among a list of attributes available for the highlighted element:

- IsVisible
- Content
- Attributes
- Style
- IsEnabled
- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Image</a>
- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">TextFromImage</a>

3.&nbsp; When crafting verifications, the suggestions' content of selected option is __dynamically built against the live selected element__. As selection of element is changed in the DOM, the suggested values are populated according to what values the current element contains.

![Verifications suggestions][3]

Building the verification sentence allows you to choose different comparison operators. 

![Comparison operators][4]

3.&nbsp; Once finished building the verification, click the **Add Step** button to insert it in the test. 

![Add Step][5]

4.&nbsp; Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the verification step and allow you to change the compare type or expected value of attribute.

![Step Properties][6]

> **Tip**
>
> You can check out the blog post dedicated on building verifications - <a href="http://blogs.telerik.com/jimholmes/posts/11-08-23/understanding-validation-content-element-types.aspx" target="_blank">**Understanding Validation Content Element Types**</a>. 

## Create a Verification Step without Recording Session

The automated test execution is much faster than a real user and often you find out it is suitable to __add an additional wait in the already recorded test__ to ensure its stability when running on different environments. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional waits.

For the cases when the project and scenarios are quite complex, you can __add verification steps for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.
<br>
__Note:__  Usually, the verification step to insert is related to an action step and its element. Thus, if you click on that action step, its target element gets highlighted in the Elements Explorer with a red arrow. Select the element and proceed to the Step Builder.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the verification you need and click the **Add Step** button to insert the step in the test. The verifications related to specific content of the element are not populated out-of-the-box and you need to __insert the expected value manually__. 

![Step Builder Verification][7]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig6.png
[7]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig7.png





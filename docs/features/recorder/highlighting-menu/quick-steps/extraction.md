---
title: Add an Extraction Step
page_title: Add an Extraction Step
description: "Test Studio provides interactive suggestions for adding extraction steps during recording based on the highlighted element. Extarction steps are useful for scenarios, which use data generated during the test run-time. Extraction steps store the value into variables and allow you reuse these later in the test steps."
position: 3
---
# Create an Extraction Step

Extraction steps in Test Studio allow you to design the automated test scenarios to use data generated dynamically during the test execution. The extraction steps can take any text based value and store into a variable. The variable can be used to data drive a value in the upcoming steps in test.

Find out more about extraction steps in the and how you can use these in the below article.

- [General notes about wait steps](#general-notes)
- [Add an extraction step](#create-an-extraction-step-in-recording-mode)
- [Use the extracted variable in the next test steps](#use-the-extracted-value-in-the-next-steps)
- [Use the extracted value in a test as step](#use-the-extracted-value-in-a-test-used-as-step)
- [Add an extraction step without recording session](#create-an-extraction-step-without-recording-session)
- [Extract the value of element attribute](#extract-the-value-of-element-attribute)

## General Notes

The Test Studio extraction steps are using the implementation for verification steps. But instead of passing or failing based on a comparison, the extraction step gets the value (text based) of an attribute for the element and stores it into a variable. The variable can be used in any of the next steps to data drive a property of the step.

The variable can be as well referenced in a sub-test used as step in the main test. In such case you need to manually type the name of the variable in the data driven property.

> **Note**
> <br>
> The engine for creating the verification sentences allows you to __convert any Verification step to Wait or Extraction step (converting to extraction step is available for text based verification)__. Use the _Change Role_ option from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> and choose from the options in the sub-menu.
> ![Change Role Option](/img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/fig0.png)

## Create an Extraction Step in Recording Mode

The <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">Highlighting menu</a> gives quick access to a set of predefined extractions, which can be added with a single click while recording. You can follow the below steps to insert a wait step in your test.

1. Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/" target="_blank">Telerik official page</a>.

1. Enable the highlighting once the recorder is attached to the browser. Hold the mouse over the __Demos__ option in the navigation menu and add a step to extract its text content.

    ![Add extract step][1]

1. Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the extraction step and allow you to change the variable name.

    ![Step Properties][2]

> __Tip__
><br>
> Extracted variables can be also used in coded steps - you can either <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">get or set their values</a>. This can help in the scenarios when you need to modify the initially extracted string before using it in the next steps.

## Use the Extracted Value in the Next Steps

Once an extraction step is added in a test, it generates a variable which holds the extracted value. __This variable is listed as available for data driving__ the properties of the test steps.

Let's continue the described test scenario and __use the extracted variable__ to type some text into the search engine on the Telerik page and check if the displayed results list that word. So, the steps added in the test are to click on the _Search_ icon, type some text in the _Search_ field, click the _Search_ button. Then verify the results count contains the typed text.

![Test Scenario][3]

1. Open the <a href="/features/test-maintenance/test-step-properties" target="_blank">properties</a> of the 'Enter text' step and expand the _Bindings_ option. The only property to data drive is the text to type and the extracted variable _DemosLink_ is listed in the dropdown as an option for data binding.

    ![Data binding properties][4]

1. In the same manner use the extracted variable to data drive the two verification steps.

    ![Data binding properties][4a]

## Use the Extracted Value in a Test Used as Step

If you need to use the extracted variable into another <a href="/features/custom-steps/test-as-step" target="_blank">test used as a step</a>, the variable name is not directly listed in the sub-test's step properties. __Type the variable name in the text box__ (without the $ notation), click on the _brackets_ icon and then the _Set_ button to use the extracted variable in the nested test:

![Bind external extracted variable][5]



## Create an Extraction Step without Recording Session

The automated test scenarios often need to be enriched with additional actons to complete the tested feature. In such cases you might need to __add a new extraction step in the already recorded test__. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional steps.

For the cases when the project and scenarios are quite complex, you can __add extarction steps for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.
<br>
__Note:__  Usually, the extraction to insert is related to an action step and its element. Thus, if you click on that action step, its target element gets highlighted in the Elements Explorer with a red arrow. Select the element and proceed to the Step Builder.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the verification type you need for the extraction and click the **Add Step** button to insert the step in the test.

![Step Builder Verification][6]

4.&nbsp; The generated step is either wait or verification step and you need to convert it to an extraction from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step properties</a> option _Change Role..._.

![Change Role][7]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

## Extract the Value of Element Attribute

The implementation of verification steps allows you to convert any text based check to an extraction. Thus you can use the value of each element attribute into an extracted variable.

1.&nbsp; Create an <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">advanced verification</a> for an attribute of an element.

![Advanced verification for attribute][8]

2.&nbsp; Switch the verification step role to an extraction step through the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step properties</a> option _Change Role..._.

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig4.png
[4a]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig4a.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/extracted-var-binding.gif
[6]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig6.png
[7]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig7.png
[8]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig8.png
[9]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig9.png

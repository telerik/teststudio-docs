---
title: Add an Extraction Step
page_title: Add an Extraction Step
description: "Test Studio provides interactive suggestions for adding extraction steps during recording based on the highlighted element. Extarction steps are useful for scenarios, which use data generated during the test run-time. Extraction steps store the value into variables and allow you reuse these later in the test steps."
position: 3
---
# Create an Extraction Step

Extraction steps in Test Studio allow you to design the automated test scenarios to use data generated dynamically during the test execution. The extraction steps can take any text based value and store into a variable. The variable can be used to data drive a value in the upcoming steps in test.

Find out more about extraction steps in the and how you can use these in the below article.

## General Notes

The Test Studio extraction steps are using the implementation for verification steps. But instead of passing or failing based on a comparison, the extraction step gets the value (text based) of an attribute for the element and stores it into a variable. The variable can be used in any of the next steps to data drive a property of the step.

The variable can be as well referenced in a sub-test used as step in the main test. In such case you need to manually type the name of the variable in the data driven propert.

> **Note**
>
> The engine for creating the verification sentences allows you to __convert any Verification step to Wait or Extracttion step (converting to extraction step is available for text based verifications)__. Use the _Change Role_ option from the <a href="/features/test-maintenance/test-step-context-menu" target="_blank">step context menu</a> and choose from the options in the sub-menu.
> ![Change Role Option](/img/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification/fig0.png)

## Create an Extraction Step in Recording Mode

The <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">Highlighting menu</a> gives quick access to a set of predefined extractions, which can be added with a single click while recording. You can follow the below steps to insert a wait step in your test.

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/" target="_blank">Telerik official page</a>.

2.&nbsp; Enable the highlighting once the recorder is attached to the browser. Hold the mouse over the __Demos__ option in the navigation menu and add a step to extract its text content.

![Add extract step][1]

3.&nbsp; Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the extraction step and allow you to change the variable name interval of checking the expected state and the overall timeout to wait for.

![Step Properties][3]








> After following the steps below, go further and <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Get/Set Extracted Variables in Code</a>.

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction#extract-an-attribute-of-an-element">Extract an attribute of an element</a>

This demonstrates how to extract a value from an element and reuse it later in your test. You can also review our Telerik TV episode on <a href="https://youtu.be/qT-_4oBwRpE" target="_blank">Using Element Extraction (Variables)</a> for a video walk-through of this process.

1.&nbsp; Highlight the desired element, choose **Quick Steps > Extract - text contains** entry. This example is against a <a href="http://www.wordgenerator.net/random-word-generator.php" target="_blank">random word generator site</a>.

![Word Generator][1]

2.&nbsp; The Extract step is added to the test.

3.&nbsp; Pause recording, double click that step, and change the DataBindVariableName. In this example I renamed it to *randomWord*.

![Extracted step added][2]

4.&nbsp; Resume recording and navigate to www.bing.com.

5.&nbsp; Enter any word into the search box and click **Submit**.

6.&nbsp; Close the browser to stop recording.

![submit][3]

7.&nbsp; Highlight the step that sets the search word for the second search engine (step 4 in this example).

8.&nbsp; Click the (**Bindings**) drop-down in the **Properties** pane.

9.&nbsp; Select the extracted variable from the value drop-down and click **Set**.

![Set][4]

10.&nbsp; Save and execute the test.

11.&nbsp; A random word is extracted from the first site and used as the query in a Bing search

> If you've <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Set an Extracted Variable in Code</a>, type the variable name in the text box (without the $ notation), click on the brackets and then _Set_:

    ![var1][5]

## Extract an attribute of an element

1.&nbsp; Create an <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">advanced verification</a> for an attribute of an element (e.g. Title). Find and select the element from the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a>.

![Advanced verification][6]

2.&nbsp; Go to the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Element Steps tab</a>

3.&nbsp; Select **Verifications** tab and choose **Attributes**. Specify the attribute that you need and click **Add Step**.

![Add Step][9]

4.&nbsp; The step is changed to an extraction one.

![Change the role][7]

5.&nbsp; The step is changed to an extraction one.

![Extraction][8]

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig6.png
[7]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig7.png
[8]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig8.png
[9]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/extraction/fig9.png

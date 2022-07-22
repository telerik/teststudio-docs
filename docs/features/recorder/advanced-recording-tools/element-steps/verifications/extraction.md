---
title: Extraction
page_title: Create an Extraction Step
description: "Create an Extraction Step in Test Studio. Use a dynamic generated value during the Test Studio test run. Reuse a dynamic value available in run-time only in Test Studio test. Get an attribute value of an element in Test Studio test. Data bind dynamic value in Test Studio test. "
position: 3
---
# Create an Extraction Step

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

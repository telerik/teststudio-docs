---
title: Extraction
page_title: Create an Extraction Step
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/verifications/data-bind-an-extraction-step.aspx, /user-guide/verifications/data-bind-an-extraction-step, /features/verifications/Extraction, /features/verifications/Extraction.html
position: 1
---
# Create an Extraction Step

> After following the steps below, go further and <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Get/Set Extracted Variables in Code</a>.

* <a href="/features/recorder/verifications/Extraction#extract-an-attribute-of-an-element">Extract an attribute of an element</a>

This demonstrates how to extract a value from an element and reuse it later in your test. You can also review our Telerik TV episode on <a href="http://www.telerik.com/videos/teststudio/using-element-extraction-(variables)-" target="_blank">Using Element Extraction (Variables)</a> for a video walk-through of this process.

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

> If you've <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Set an Extracted Variable in Code</a>, type the variable name in the text box (without the $ notation), click on the brackets and then Set: 

![var1][5]

## Extract an attribute of an element

1.&nbsp; Create an <a href="/features/recorder/verifications/advanced-verification" target="_blank">advanced verification</a> for an attribute of an element (e.g. Title).

![Advanced verification][6]

If the element is **hidden** you should select it from the DOM Explorer

![DOM Selection][9]

2.&nbsp; Change the role of the verification step to Extraction.

![Change the role][7]

3.&nbsp; The step is changed to an extraction one.

![Extraction][8]

[1]: /img/features/recorder/verifications/extraction/fig1.png
[2]: /img/features/recorder/verifications/extraction/fig2.png
[3]: /img/features/recorder/verifications/extraction/fig3.png
[4]: /img/features/recorder/verifications/extraction/fig4.png
[5]: /img/features/recorder/verifications/extraction/fig5.png
[6]: /img/features/recorder/verifications/extraction/fig6.png
[7]: /img/features/recorder/verifications/extraction/fig7.png
[8]: /img/features/recorder/verifications/extraction/fig8.png
[9]: /img/features/recorder/verifications/extraction/fig9.png

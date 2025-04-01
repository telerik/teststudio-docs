---
title: Pass a Variable
page_title: Pass a Variable
description: An example how to reuse a dynamically extracted variable (during runtime) in different tests.
position: 1
---
## Pass a Variable Between Tests

I would like to capture data in one test and pass it to another. Is it possible to set a variable in one test and have it accessible by another test in the project?

## Solution

This is possible using the <a href="/features/recorder/verifications/Extraction" target="_blank">Extraction</a> and <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a> features.

1. Create a project and add two tests: Parent and Child.

2. Open the Parent test.

3. Click **Record** and navigate to a <a href="http://watchout4snakes.com/wo4snakes/Random/RandomWordPlus" target="_blank">random word generator site</a>.

4. Perform an Extraction on the word.

	![Extract][1]

5. Edit the *DataBindVariableName* for the Extract step.

	![Rename the variable][2]

6. Open the Child test.

7. Record steps that navigate to *www.bing.com*, enter a search query, and click the submit button.

8. <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">Bind</a> the variable to the Enter Text step. Type the name of the variable manually (*randomWord*), click the **brackets** and the **Set** button.

	![Bind the child test][3]

9. Load the Parent test again.

10. Add the Child test to it via the <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a> feature.

	![Test as Step][4]

11. Execute the Parent test.


12. The random word is extracted in the Parent test and used as the search query in the Child test.

> You can also perform an Extraction in the Child test and pass that variable back to the Parent test.

[1]: /img/knowledge-base/data-driven-testing-kb/pass-a-variable/fig1.png
[2]: /img/knowledge-base/data-driven-testing-kb/pass-a-variable/fig2.png
[3]: /img/knowledge-base/data-driven-testing-kb/pass-a-variable/fig3.png
[4]: /img/knowledge-base/data-driven-testing-kb/pass-a-variable/fig4.png

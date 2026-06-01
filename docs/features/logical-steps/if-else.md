---
title: If...Else
page_title: If...Else
description: "Logical steps in Test Studio. If else block in Test Studio. Can I build an if else conditions in Tets Studio test. "
previous_url: /user-guide/logical-steps/if-else.aspx, /user-guide/logical-steps/if-else
position: 1
---
# If...Else

Test Studio provides built-in conditions for the test scenarios which cannot be covered by a simple sequence of actions. One of the available conditions is the if..else block to determine how to proceed the test based on a specific condition.

In this article you can find the following topics:

* [Add the if..else condition and setup the test steps](#build-an-ifelse-statement)
* [Explore the outcome of running the test](#execution-status-and-results)
* [An example how to verify if an element exists on the page](#check-if-an-element-exists-in-the-dom)

> __Tip__
> Check this <a href="https://www.telerik.com/blogs/test-studio-step-by-step-testing-execution-paths-conditional-tests">step-by-step tutorial blog post</a> on how to enhance your test scenarios with conditional steps.

## Build an If...Else Statement

1. Create a Web Test and click Record.

2. Navigate to <a href="https://www.calculator.net/random-number-generator.html" target="_blank">www.random.org</a>.

3. Set the Min field to 1 and the Max field to 2.

4. Click **Generate**.

    ![Random](/img/features/logical-steps/if-else/rnd-num-gen-page.png)

5. Enable hover over highlighting by clicking Highlight Element in the Test Studio Recorder and hover over the *Result box*.

    ![Enable Highlighting](/img/features/logical-steps/if-else/quick-step-drop-down.png)

6. Click **Quick Tasks** and double click **Verify - text contains '1'**.

    ![Verification](/img/features/logical-steps/if-else/verify-step-choose.png)

7. Disable hover over highlighting and minimize the browser.

8. Choose **Conditions** in the <a href="/getting-started/test-recording/step-suggestions" target="_blank">**Step Builder**</a> and add **if...else** step.

<table id="no-table" style="border:none;">
<tr style="text-align: center; background-color: transparent; border:none;">
<td>

<img src="/img/features/logical-steps/if-else/step-builder-if-else.png" alt="Standalone" /><br>**Standalone version**</td>
<td>

<img src="/img/features/logical-steps/if-else/vs-step-builder.png" alt="VS Plugin" /><br>**VS Plugin**</td>
<tr>
</table>

9. From the drop down in the IF step select the previously recorded verification.

    ![Choose Verification](/img/features/logical-steps/if-else/select-condition-in-if.png)

10. Uncheck/Delete the verification outside the IF step, so it will not be executed (We have this verification already added in the IF step)

    ![Uncheck Verification](/img/features/logical-steps/if-else/uncheck-verify-step.png)

11. Bring up the IE recording window and navigate to <a href="http://www.google.com" target="_blank">www.google.com</a>. Minimize the browser again.

12. Drag the *Navigate to Google* step into the IF step.

![Drag in IF Step](/img/features/logical-steps/if-else/drop-inside-if.png)

13. Bring up the IE recording window and navigate to <a href="http://www.bing.com" target="_blank">www.bing.com</a>. Minimize the browser again.

14. Drag the *Navigate to Bing* step into the ELSE step.

![Drag in ELSE Step](/img/features/logical-steps/if-else/drop-inside-else.png)

## Execution Status and Results

15. Save and Execute the test.

- If 1 is generated the **if condition** is evaluated as true and the steps in the **if branch** are executed. The steps in the **else branch** are skipped and shown as 'Not Run'.

![Navigate to Google](/img/features/logical-steps/if-else/if-executed.png)

- If 2 is generated the **if condition** is evaluated as false (for example, the target TextBox element contains the wrong content) and the steps in the **else branch** are executed. The skipped steps are in the **if branch** and are shown as 'Not Run'. 
- **Note**:  if the condition of an **if branch** cannot be evaluated (for example, the target element for a TextContent verification cannot be located), the steps in the **if branch** will be skipped again, and will display a 'not-run' icon as if the condition is false. 

![Navigate to Bing](/img/features/logical-steps/if-else/else-executed.png)

## Check if an Element Exists in the DOM

To check if an element is present in the application DOM - a "<a href="/features/recorder/verifications/Wait" target="_blank">wait on element</a>" verification has to be used. It returns *true/false* output and **if condition** could be completed not braking the test execution. On the following image - if step 4 does not execute - the *SecondLink* element would not be added to the DOM and steps would continue in the **else branch**.

![If Element Exists](/img/features/logical-steps/if-else/elem-in-dom-exist-1.png)

If step 4 is executed the *SecondLink* element would be added to the DOM and **if condition** passes normally as shown below.

![Else Element Exists](/img/features/logical-steps/if-else/elem-in-dom-exist-if.png)


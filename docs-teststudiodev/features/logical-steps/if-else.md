---
title: If...Else
page_title: If...Else - Test Studio Dev Documentation
description: How to build a if...else with Test Studio Dev 
slug: features/logical-steps/if-else
position: 1
---
# If...Else

Walk-through the IF...Else conditional statement process - <a href="/features/logical-steps/if-else#Build-a-new-IfElse-Statement">how to build a meaningful if...else statement</a>, <a href="/features/logical-steps/if-else#Execution-status-and-Results">what the execution status looks like</a> and a sample on <a href="/features/logical-steps/if-else#Check-if-an-element-exists-in-the-DOM">how to check if an element exists in the DOM</a>.

## Build a new If...Else Statement

1.&nbsp; Create a Web Test and click Record.

2.&nbsp; Navigate to <a href="https://www.random.org/" target="_blank">www.random.org</a>.

3.&nbsp; Set the Min field to 1 and the Max field to 2.

4.&nbsp; Click **Generate**.

![Random][1]

5.&nbsp; Enable hover over highlighting by clicking Highlight Element in the Test Studio Recorder and hover over the *Result box*.

![Enable Highlighting][2]

6.&nbsp; Click **Quick Tasks** and double click **Verify - text contains '1'**.

![Verification][3]

7.&nbsp; Disable hover over highlighting and minimize the browser.

8.&nbsp; Choose **Conditions** in the <a href="/features/recorder/step-builder">**Step Builder**</a> and add **if...else** step.

![VS Plugin][13]


9.&nbsp; From the drop down in the IF step select the previously recorded verification.

![Choose Verification][6]

10.&nbsp; Uncheck/Delete the verification outside the IF step, so it will not be executed (We have this verification already added in the IF step)

![Uncheck Verification][7]

11.&nbsp; Bring up the IE recording window and navigate to <a href="http://www.google.com" target="_blank">www.google.com</a>. Minimize the browser again.

12.&nbsp; Drag the *Navigate to Google* step into the IF step.

![Drag in IF Step][8]

13.&nbsp; Bring up the IE recording window and navigate to <a href="http://www.bing.com" target="_blank">www.bing.com</a>. Minimize the browser again.

14.&nbsp; Drag the *Navigate to Bing* step into the ELSE step.

![Drag in ELSE Step][9]

## Execution status and Results

15.&nbsp; Save and Execute the test.

- If 1 is generated the **if condition** is evaluated as true and the steps in the **if branch** are executed. The steps in the **else branch** are skipped and shown as 'Not Run'.

![Navigate to Google][10]

- If 2 is generated the **if condition** is evaluated as false (for example, the target TextBox element contains the wrong content) and the steps in the **else branch** are executed. The skipped steps are in the **if branch** and are shown as 'Not Run'. 
- **Note**:  if the condition of an **if branch** cannot be evaluated (for example, the target element for a TextContent verification cannot be located), the steps in the **if branch** will be skipped again, and will display a 'not-run' icon as if the condition is false. 

![Navigate to Bing][11]

## Check if an element exists in the DOM

To check if an element is present in the application DOM - a "<a href="/features/recorder/verifications/Wait" target="_blank">wait on element</a>" verification has to be used. It returns *true/false* output and **if condition** could be completed not braking the test execution. On the following image - if step 4 does not execute - the *SecondLink* element would not be added to the DOM and steps would continue in the **else branch**.

![If Element Exists][14]

If step 4 is executed the *SecondLink* element would be added to the DOM and **if condition** passes normally as shown bellow.

![Else Element Exists][15]

[1]: images/if-else/fig1.png
[2]: images/if-else/fig2.png
[3]: images/if-else/fig3.png


[6]: images/if-else/fig6.png
[7]: images/if-else/fig7.png
[8]: images/if-else/fig8.png
[9]: images/if-else/fig9.png
[10]: images/if-else/fig10.png
[11]: images/if-else/fig11.png

[13]: images/if-else/fig13.png
[14]: images/if-else/fig14.png
[15]: images/if-else/fig15.png

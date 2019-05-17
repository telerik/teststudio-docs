---
title: Loop
page_title: Loop
description: "Loop a repeating action certain amount of times in Test Studio test. Loop cycle in Test Studio test"
previous_url: /user-guide/logical-steps/loop.aspx, /user-guide/logical-steps/loop
position: 1
---
# Loop

Walk--through of creating a loop process.

1.&nbsp; Create a Web Test and click **Record**.

2.&nbsp; Navigate to <a href="http://www.random.org/integers/" target="_blank">www.random.org/integers</a>.

3.&nbsp; Click Get Numbers. 

4.&nbsp; Click Again.

![Random][1]

5.&nbsp; Pause recording and minimize the browser.

6.&nbsp; Choose **Conditions** in the <a href="/getting-started/test-recording/step-suggestions" target="_blank">**Step Builder**</a> and add **loop** step.

<table id="no-table">
<tr>
<td>![Standalone][6]<br>**Standalone version**</td>
<td>![VS Plugin][7]<br>**VS Plugin**</td>
<tr>
<table>

7.&nbsp; Set the *Count* of the Loop step to 5.

![Loop step count][4]

8.&nbsp; Drag the second Click Submit step into the *LOOP* step.

![Drag Submit][5]

9.&nbsp; Save and Execute. After the initial set of integers is generated, the process is repeated 5 times.

[1]: /img/features/logical-steps/loop/fig1.png
[4]: /img/features/logical-steps/loop/fig4.png
[5]: /img/features/logical-steps/loop/fig5.png
[6]: /img/features/logical-steps/loop/fig6.png
[7]: /img/features/logical-steps/loop/fig7.png
---
title: Loop
page_title: Loop
description: "Loop a repeating action certain amount of times in Test Studio test. Loop cycle in Test Studio test"
previous_url: /user-guide/logical-steps/loop.aspx, /user-guide/logical-steps/loop
position: 1
---
# Loop

Walk--through of creating a loop process.

1. Create a Web Test and click **Record**.

2. Navigate to <a href="http://www.random.org/integers/" target="_blank">www.random.org/integers</a>.

3. Click Get Numbers. 

4. Click Again.

![Random](/img/features/logical-steps/loop/fig1.png)

5. Pause recording and minimize the browser.

6. Choose **Conditions** in the <a href="/getting-started/test-recording/step-suggestions" target="_blank">**Step Builder**</a> and add **loop** step.

<table id="no-table" style="border:none;">
<tr style="text-align: center; background-color: transparent; border:none;">
<td>

<img src="/img/features/logical-steps/loop/step-builder-loop.png" alt="Standalone" /><br>**Standalone version**</td>
<td>

<img src="/img/features/logical-steps/loop/vs-step-builder.png" alt="VS Plugin" /><br>**VS Plugin**</td>
<tr>
</table>

7. Set the *Count* of the Loop step to 5.

![Loop step count](/img/features/logical-steps/loop/extended-menu-loop.png)

8. Drag the second Click Submit step into the *LOOP* step.

![Drag Submit](/img/features/logical-steps/loop/drag-drop-loop.png)

9. Save and Execute. After the initial set of integers is generated, the process is repeated 5 times.

---
title: Loop
page_title: Loop - Test Studio Dev Documentation
description: How to build a loop with Test Studio Dev 
slug: features/logical-steps/loop
tags: loop, verification
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

6.&nbsp; Choose **Conditions** in the <a href="/features/recorder/step-builder">**Step Builder**</a> and add **loop** step.

![VS Plugin][7]

7.&nbsp; Set the *Count* of the Loop step to 5.

![Loop step count][4]

8.&nbsp; Drag the second Click Submit step into the *LOOP* step.

![Drag Submit][5]

9.&nbsp; Save and Execute. After the initial set of integers is generated, the process is repeated 5 times.

[1]: images/loop/fig1.png
[4]: images/loop/fig4.png
[5]: images/loop/fig5.png
[6]: images/loop/fig6.png
[7]: images/loop/fig7.png
---
title: Wait
page_title: Create a Wait Step
description: "Test Studio Wait Step. Add a step to wait for specific element /element state in Test Studio test. My test is failing on random step by each execution. Can I slow down the Test Studio test execution depending on how fast the automated page application loads the elements."
position: 1
---
# Create a Wait Step

You can create a Wait step in the same manner as a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">quick verification</a> step. Instead of passing or failing based on a comparison, this step will wait for the comparison to be true before proceeding. The verification is performed after the server has responded.

> **Tip**
> <br>
> <br>
> Check out this <a href="https://www.youtube.com/watch?v=Klt3fRglAeU&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=3">video tutorial</a> about wait and verification steps in Test Studio.

1.&nbsp; Highlight the desired element. From the menu that appears choose **Quick Steps > Wait - element exists**.

![Wait element exists][1]

2.&nbsp; The Wait step is added to the test.

![Wait step added][2]

3.&nbsp; With the Wait step highlighted, you can see the test step properties where you can change the Check interval and the timeout.

![Step Properties][3]

4.&nbsp; You can also toggle a verify step between Verification, Wait, and Extraction (if based on text). Right click the step and select __Change Role > Set As...__

![Set as Wait][4]

<br />
<br />
<br />

__See Also...__

* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick verification</a>
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced verification</a>

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/wait/fig4.png

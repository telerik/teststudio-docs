---
title: Fast Forward Test
page_title: Fast Forward Manual Test 
description: "Fast Forward Test Run of a manual test in Test Studio."
previous_url: /user-guide/manual-testing/fast-forward-test.aspx, /user-guide/manual-testing/fast-forward-test
position: 3
---
# Fast Forward Test

Speed up the manual testing process by automating some (or eventually all) of the test steps.

1.&nbsp; Once you have a Manual Test written, click the **Fast Forward Test** button in the **Next Steps** ribbon.

![Fast Forward][1]

2.&nbsp; Choose whether this is to be a Web or WPF Test. In this example I chose Web Test.

![Choose Test][2]

3.&nbsp; The Manual Test is imported into a Web Test environment, consisting entirely of <a href="/features/custom-steps/manual-step" target="_blank">Manual Steps</a>.

![Add manual][3]

4.&nbsp; Now use the <a href="/getting-started/test-recording/overview" target="_blank">Recorder</a> to replace manual steps with automated steps, or add new ones.

![Automated][4]

5.&nbsp; Click **Execute** in the **Quick Execution** ribbon. You are still presented with the Manual Test execution dialog. However, you have the option to fast forward the selected automated steps to speed up testing.

![Execute][5]

6.&nbsp; Are you running a Web or WPF Test?

a. For a Web Test: Click the **Launch new browser** drop-down, select a browser, then click **Continue**.

![Launch New Browser][6]

b. For a WPF Test: Click the **Browse** button to enter where the app is located, click **Launch App**, then click **Continue**.

![Launch App][7]

7.&nbsp; Select one or more automated steps (using Ctrl or Shift + Click) and click the **Selected** button to run the highlighted automated steps.

![Selected][8]

8.&nbsp; Once the next manual step is reached, proceed as normal and mark it as Pass, Fail, or NotRun. Capture a desktop screen shot and write notes for any step as you test.

![Fail][9]

9.&nbsp; Continue this way until the test is complete. Then select either:

- **Save & Close** - return to the Record tab.
  - For a failed automated step, double click the red and white "X" icon next to it to see the Step Failure Details.
  - For a failed manual step, double click the red and white "X" icon next to it to see the screen shot and notes.

![X icon][10]

- **Reset Results** - discard current results and return to the Manual Test execution dialog. You are prompted to save the .aiiresult file (optional). That file type can be opened with the Test Studio Result Viewer.

![Results][11]

[1]: /img/features/testing-types/manual-testing/fast-forward/fig1.png
[2]: /img/features/testing-types/manual-testing/fast-forward/fig2.png
[3]: /img/features/testing-types/manual-testing/fast-forward/fig3.png
[4]: /img/features/testing-types/manual-testing/fast-forward/fig4.png
[5]: /img/features/testing-types/manual-testing/fast-forward/fig5.png
[6]: /img/features/testing-types/manual-testing/fast-forward/fig6.png
[7]: /img/features/testing-types/manual-testing/fast-forward/fig7.png
[8]: /img/features/testing-types/manual-testing/fast-forward/fig8.png
[9]: /img/features/testing-types/manual-testing/fast-forward/fig9.png
[10]: /img/features/testing-types/manual-testing/fast-forward/fig10.png
[11]: /img/features/testing-types/manual-testing/fast-forward/fig11.png

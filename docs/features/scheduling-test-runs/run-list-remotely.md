---
title: Run List Remotely
page_title: Run List Remotely
description: "Test Studio test list executed run on remote machine"
previous_url: /user-guide/scheduling-test-runs/run-list-remotely.aspx, /user-guide/scheduling-test-runs/run-list-remotely
position: 8
---
# Run List Remotely

Once you've correctly configured a Scheduling Server and you've attached at least one Execution Server to it, you can proceed with executing a test run remotely.

## Schedule Test List Execution

1.&nbsp; Open the **Test Lists** tab. If you have not created a test list, add one by clicking the **List** button in the **Add** ribbon. Add at least one test to it.

2.&nbsp; Once you have a test list, you can run it remotely. Click **Run List Remotely** in the **Execution** ribbon.

![Run List Remotely][1]

3.&nbsp; Select the execution machine(s) for your test list.

![Select Test List][2]

4.&nbsp; In case a test is already running on any of the listed machines its status will be Busy and the listing will be grayed out. 

![Busy Status][8]

5.&nbsp; A message appears indicating that your tests are now running. Click **close** to return to the **Test Lists** tab.

![Close][3]

## View Test List Results 

Go to the **Results** tab to view the outcome. <a href="/features/scheduling-test-runs/scheduling-results" target="_blank">See here</a> for further information.

![Results][4]

## View Execution Details

1.&nbsp; On the Execution Server, right-click the Test Studio Test Runner icon in the System Tray and click Show. 

![Show][5]

2.&nbsp; Click **Process History** > **GUI Test Runner**. The execution details will appear on the right.

![GUI Test Runner][6]

3.&nbsp; To export remote execution details, click the correct format button in the **Remote Execution Details** pane.

![Remote Execution Details][7]

[1]: /img/features/scheduling-test-runs/run-list-remotely/fig1.png
[2]: /img/features/scheduling-test-runs/run-list-remotely/fig2.png
[3]: /img/features/scheduling-test-runs/run-list-remotely/fig3.png
[4]: /img/features/scheduling-test-runs/run-list-remotely/fig4.png
[5]: /img/features/scheduling-test-runs/run-list-remotely/fig5.png
[6]: /img/features/scheduling-test-runs/run-list-remotely/fig6.png
[7]: /img/features/scheduling-test-runs/run-list-remotely/fig7.png
[8]: /img/features/scheduling-test-runs/run-list-remotely/fig8.png

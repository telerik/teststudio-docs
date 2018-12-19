---
title: Connect to Scheduling Server
page_title: Connect a Project to the Scheduling Server
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/scheduling-test-runs/connect-a-project-to-a-scheduling-server.aspx, /user-guide/scheduling-test-runs/connect-a-project-to-a-scheduling-server
position: 7
---
# Connect a Project to the Scheduling Server

Once you've configured your Scheduling Server and you've successfully registered at least one Execution Server to it, you're ready to configure a test project for execution. 

**Note**: It is not necessary to configure a Scheduling Server in order to schedule <a href="/features/scheduling-test-runs/overview#local-run" target="_blank">local test executions</a>.

From Test Studio Standalone version, load a new test project that contains at least one test and test list. Now connect the project to the Scheduling Server. Keep in mind that the Scheduling Server doesn't have to be on the same machine as the instance of Test Studio you're using.

1.&nbsp; Click **Connect** in the **Scheduling** ribbon on the **Project** tab. 

![Connect][1]

2.&nbsp; In the **Scheduling Server Settings** dialog, click the radio box next to the correct scheduling setup option: 

- To schedule a test to run on the local machine, click **Run locally**.

![Run Locally][2]
- To schedule a test to run on a remote machine, click **Run remotely**. Enter the address for the remote scheduling server and click **Connect**.

![Run Remotely][3]

[1]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig1.png
[2]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig2.png
[3]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig3.png


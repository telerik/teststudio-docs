---
title: Connect a Project to Scheduling Server
page_title: Configure a Test Studio Project for Remote Execution
description: "Connect the Test Studio project to the configured Scheduling Server to run test lists on remote machines. Unable to choose the connected execution machines to run test lists on these. Configure a project to execute tests from it remotely,Configure a Test Studio Project for Remote Execution"
position: 5
---
# Connect a Project to the Scheduling Server

Once you've <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured your Scheduling setup</a> and you've successfully <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-execution-server#configure-test-studio-test-runner" target="_blank">registered at least one Execution Server to it</a>, you are ready to configure a test project for remote execution.

## Schedule Test Lists on Remote Execution Machines

Open a Test Studio project in the tool's standalone version, create at least one test and a test list. In the **Project** tab click **Connect** in the **Scheduling** ribbon.

![Connect][1]

In the following **Scheduling Server Settings** dialog, click **Run remotely** to schedule a test to run on the connected remote machine(s). Enter the address for the remote scheduling server and click **Connect**.

![Run Remotely][3]

## Schedule Tests on Single Machine

If you haven't configured the Test Studio service, you still can schedule test lists on the local machine, choose the **Run locally** option in the **Scheduling Server Settings** dialog and click **Connect**.

![Run Locally][2]

[1]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig1.png
[2]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig2.png
[3]: /img/features/scheduling-test-runs/connect-to-scheduling-server/fig3.png

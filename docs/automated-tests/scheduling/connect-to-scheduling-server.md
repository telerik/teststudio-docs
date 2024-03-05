---
title: Connect a Project to Scheduling Server
page_title: Configure a Test Studio Project for Remote Execution
description: "Connect the Test Studio project to the configured Scheduling Server to run test lists on remote machines. Unable to choose the connected execution machines to run test lists on these. Configure a project to execute tests from it remotely,Configure a Test Studio Project for Remote Execution"
position: 5
---
# Connect a Project to the Scheduling Server

Once you've <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured your Scheduling setup</a> and you've successfully <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-execution-server#configure-test-studio-test-runner" target="_blank">registered at least one Execution Server to it</a>, you are ready to configure a test project for remote execution.

This article guides you how to connect:

- [To a Scheduling server for remote execution](#connect-the-project-to-schedule-test-lists-on-remote-execution-machines)
- [To a Reverse Proxy server behind which is the Scheduling server](#connect-via-reverse-proxy-advanced)

## Connect the Project to Schedule Test Lists on Remote Execution Machines

Open the Test Studio project and click the **Connect** button from the `Scheduling` ribbon in the **Project** tab.

![Connect][1]

In the **Scheduling Server Settings** dialog, choose **Remote** radio button to connect the project to the configured Scheduling server. 

![Run Remotely][5a]

### Communication Key 

The __Communication Key__ lets you import the key generated in the Scheduling Config wizard. The text field remains empty to keep safe the value of the key in use. To indicate a key is in use ensure the **Loaded.** status is present.

> **Tip**
><br> 
><br> In case the communication key is not matching, you need to import the current key in use. Check <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here how to generate a new key and import it for all Scheduling components</a>. 

### Server Name

Enter the machine name for the machine which hosts the Scheduling service, then click **Connect**.

![Connect to Scheduling machine][5]

A confirmation message appears when the connection is successful. 

## Confirm Connection 

Once the connection is successfully established, click the **Confirm** button to apply the changes in the project. 

## Connect via Reverse Proxy (Advanced)

Test Studio allows you to connect a project to a Scheduling server hosted in a network behind a Reverse Proxy server. See <a href="/automated-tests/scheduling/advanced-topics/connect-via-proxy-server" target="_blank">the detailed instructions on the required configuration to setup this connection</a>. 

![Reverse proxy connect][1a]

[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png
[5a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5a.png
[5]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png

[1a]: /img/features/scheduling-test-runs/connect-via-proxy/fig1a.png
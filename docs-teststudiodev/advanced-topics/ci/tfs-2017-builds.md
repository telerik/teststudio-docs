---
title: TFS 2017 Builds
page_title: TFS 2017 Test Execution | Test Studio Dev Documentation
description: TFS 2017 Test Execution of Test Studio Dev tests
position: 3
---
# TFS 2017 Builds Test Execution

**TFS 2017** supports integration with external command line utility where <a href="/features/cli-runner" target="_blank">**ArtOfTest.Runner.exe**</a> can be used.

1. Create a new **build definition**:

![Empty Build Definition][1]

2. Choose **Empty process** template:

![Empty Process Template][2]

3. Add a new **build task**. Choose **Utility** from the catalog on the left and select a **Command line task**:

![Add a build task][3]

4. Once the step is created you need to provide the **ArtOfTest.Runner.exe location and arguments** to the command line. The default location of the tool is C:\Program Files (x86)\Progress\Test Studio\Bin. More details about the required arguments are <a href="/features/cli-runner" target="_blank">**here**</a>.

![Configure CLI step][4]

The root folder of the test project should be accessible from the TFS server. In the example we use a project stored on a shared location (source controlled project can be used as well).

5. A TFS agent should be configured and **it should be set to run in interactive mode**. Further details how to download, install and configure the agent is in the Agent Queues section on TFS server control panel. 

![Agent Queues View][5]

Once the agent is successfully installed, run it in interactive mode. It will be available in the **Agents Queues** view under the Default queue and will be marked green in case it is up and running or red in case the agent is not detected.

![Agents Queue][6]

6. You can now queue the build from the **Task view**: 

![Queue a build][7]

8. The build will **start the ArtOfTest.Runner** and execute the tests or tests lists.

![Build succeeded][8]


[1]: images/tfs2017/fig1.png
[2]: images/tfs2017/fig2.png
[3]: images/tfs2017/fig3.png
[4]: images/tfs2017/fig4.png
[5]: images/tfs2017/fig5.png
[6]: images/tfs2017/fig6.png
[7]: images/tfs2017/fig7.png
[8]: images/tfs2017/fig8.png
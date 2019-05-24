---
title: VS Team Services Builds
page_title: VS Team Services Azure DevOps Test Execution
description: "Integrate Test Studio tests in VS Team Services, Azure DevOps, online TFS continuous integration. Execute Test Studio tests with VS Team Services. Azure DevOps, online TFS build."
position: 9
---
# VS Team Services/ Azure DevOps Test Execution #

**VS Team Services** supports integration with external command line utility where <a href="/features/test-runners/artoftest-runner" target="_blank">**ArtOfTest.Runner.exe**</a> could be plugged in.

1.&nbsp; Create a new plain **build definition**: 

![Empty Build Definition][1]

2.&nbsp; Choose **default agent queue** on the next step of creation: 

![Default Agent Queue][2]

3.&nbsp; Add a **build step**: 

![Add a build step][3]

4.&nbsp; Choose **Utility** from the catalog on the left and select a **Command line step**: 

![Command line build step][4]

5.&nbsp; Once the step is added you need to close the catalog and provide the **ArtOfTest.Runner.exe location and arguments to pass** to it. The default location of the tool is C:\Program Files (x86)\Telerik\Test Studio\Bin. Further details about the required arguments could be found <a href="/features/test-runners/artoftest-runner" target="_blank">**here**</a>.

![Configure CLI step][5]

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

When you choose to save the step you could rename it with a meaningful to you name. 

![Save and Rename CLI step][6]

6.&nbsp; An agent should be configured and **mandatory run in interactive mode**. Further details how to download, install and configure the agent could be found <a href="https://www.visualstudio.com/en-us/docs/build/admin/agents/v2-windows" target="_blank">**here**</a>. 

Once the agent is successfully installed run it in interactive mode. It will be available in the **Agents Queues** view in the VS Team Services under the Default queue and will be marked green in case it is up and running or red in case the agent could not be detected.   

![Agents Queue][9]

7.&nbsp; Back in VS Team Services **queue a new build** for the newly created CLI step: 

![Queue a build for the CLI step][7]

8.&nbsp; The build should now successfully **start the ArtOfTest.Runner** and execute the tests or test lists from the provided arguments. 

![Build succeeded][8]

[1]: /img/advanced-topics/build-server/vs-team-services-builds/EmptyBuildDefinition.png
[2]: /img/advanced-topics/build-server/vs-team-services-builds/fig2.png
[3]: /img/advanced-topics/build-server/vs-team-services-builds/fig3.png
[4]: /img/advanced-topics/build-server/vs-team-services-builds/fig4.png
[5]: /img/advanced-topics/build-server/vs-team-services-builds/fig5.png
[6]: /img/advanced-topics/build-server/vs-team-services-builds/fig6.png
[7]: /img/advanced-topics/build-server/vs-team-services-builds/fig7.png
[8]: /img/advanced-topics/build-server/vs-team-services-builds/fig8.png
[9]: /img/advanced-topics/build-server/vs-team-services-builds/fig9.png
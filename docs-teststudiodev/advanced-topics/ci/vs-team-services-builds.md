---
title: VS Team Services Builds
page_title: VS Team Services Test Execution - Test Studio Dev Documentation
description: VS Team Services Test Execution of Test Studio Dev tests
position: 4
---
# VS Team Services Test Execution 

**VS Team Services** supports integration with external command line utility where <a href="/features/cli-runner" target="_blank">**ArtOfTest.Runner.exe**</a> could be plugged in.

1. Create a new plain **build definition**: 

![Empty Build Definition][1]

2. Choose **default agent queue** on the next step of creation: 

![Default Agent Queue][2]

3. Add a **build step**:

![Add a build step][3]

4. Choose **Utility** from the catalog on the left and select a **Command line step**:

![Command line build step][4]

5. Once the step is added you need to close the catalog and provide the **ArtOfTest.Runner.exe location and arguments to pass** to it. The default location of the tool is C:\Program Files (x86)\Telerik\Test Studio\Bin. Further details about the required arguments could be found <a href="/features/cli-runner" target="_blank">**here**</a>.

![Configure CLI step][5]

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

When you choose to save the step you could rename it with a meaningful to you name. 

![Save and Rename CLI step][6]

6. An agent should be configured and **mandatory run in interactive mode**. Further details how to download, install and configure the agent could be found <a href="https://www.visualstudio.com/en-us/docs/build/admin/agents/v2-windows" target="_blank">**here**</a>.

Once the agent is successfully installed run it in interactive mode. It will be available in the **Agents Queues** view in the VS Team Services under the Default queue and will be marked green in case it is up and running or red in case the agent could not be detected.

![Agents Queue][9]

7. Back in VS Team Services **queue a new build** for the newly created CLI step:

![Queue a build for the CLI step][7]

8. The build should now successfully **start the ArtOfTest.Runner** and execute the tests or test lists from the provided arguments.

![Build succeeded][8]

[1]: images/vstservice/EmptyBuildDefinition.png
[2]: images/vstservice/fig2.png
[3]: images/vstservice/fig3.png
[4]: images/vstservice/fig4.png
[5]: images/vstservice/fig5.png
[6]: images/vstservice/fig6.png
[7]: images/vstservice/fig7.png
[8]: images/vstservice/fig8.png
[9]: images/vstservice/fig9.png
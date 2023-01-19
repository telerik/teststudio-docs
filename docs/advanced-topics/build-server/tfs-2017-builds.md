---
title: TFS 2017 Builds
page_title: TFS 2017 Test Execution
description: "Integrate Test Studio tests in TFS 2017 continuous integration. Execute Test Studio tests with TFS 2017 build."
position: 9
---
# TFS 2017 Builds Test Execution

**TFS 2017** supports integration with external command line utility where <a href="/features/test-runners/artoftest-runner" target="_blank">**ArtOfTest.Runner.exe**</a> could be plugged in to execute the <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests.

The below steps will guide you through the process how to implement the Test Studio tests execution in TFS 2017 builds.

1.&nbsp; Create a new **build definition**:

![Empty Build Definition][1]

2.&nbsp; Choose **Empty process** template on the next step of creation:

![Empty Process Template][2]

3.&nbsp; Add a new **build task**. Choose **Utility** from the catalog on the left and select a **Command line task**:

![Add a build task][3]

4.&nbsp; Once the step is added you need to provide the **ArtOfTest.Runner.exe location and arguments to pass** to the command line. The default location of the tool is C:\Program Files (x86)\Progress\Test Studio\Bin. Further details about the required arguments could be found <a href="/features/test-runners/artoftest-runner" target="_blank">**here**</a>.

![Configure CLI step][4]

The project to execute a test list from should be accessible from the TFS server but is not mandatory to be included under source control on the same server. The current example executes a test list from project stored on a shared location.

5.&nbsp; A TFS agent should be configured and **mandatory run in interactive mode**. Further details how to download, install and configure the agent could be found in the Agent Queues section on TFS server. 

![Agent Queues View][5]

Once the agent is successfully installed run it in interactive mode. It will be available in the **Agents Queues** view under the Default queue and will be marked green in case it is up and running or red in case the agent could not be detected.

![Agents Queue][6]

6.&nbsp; Back in the **Task view** for the newly created build definition you could queue a build to run: 

![Queue a build][7]

8.&nbsp; The build should now successfully **start the ArtOfTest.Runner** and execute the tests or test lists from the provided arguments.

![Build succeeded][8]

__See Also:__ You may find helpful our blog post <a href="https://www.telerik.com/blogs/how-to-utilize-test-studio-tests-in-your-tfs-ci-builds" target="_blank">__How to Utilize Test Studio Tests in Your TFS CI Builds__</a>.

[1]: /img/advanced-topics/build-server/tfs-2017-builds/fig2.png
[2]: /img/advanced-topics/build-server/tfs-2017-builds/fig2.png
[3]: /img/advanced-topics/build-server/tfs-2017-builds/fig3.png
[4]: /img/advanced-topics/build-server/tfs-2017-builds/fig4.png
[5]: /img/advanced-topics/build-server/tfs-2017-builds/fig5.png
[6]: /img/advanced-topics/build-server/tfs-2017-builds/fig6.png
[7]: /img/advanced-topics/build-server/tfs-2017-builds/fig7.png
[8]: /img/advanced-topics/build-server/tfs-2017-builds/fig8.png

---
title: Azure DevOps 
page_title: Azure DevOps Build Pipeline
description: "Integrate Test Studio tests in Azure DevOps Build Pipeline continuous integration. Execute Test Studio tests with Azure DevOps Build Pipeline."
position: 2
---
# Test Studio Tests and Azure DevOps Build Pipeline

<a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests can be successfully integrated for execution with the Azure DevOps Build pipelines. Below you can read details for the prerequisites and necessary configurations to apply.

## Environmental Prerequisites

The build machine can be any virtual or physical machine to host the Test Studio Runner. Please refer to the <a href="/system-requirements" target="_blank">system requirements</a> for the required machine configuration.

The components to be installed on the machine:

* __Test Studio Run-time Edition__ (ArtOfTest.Runner.exe must be available): __mandatory__
* __Internet Browser__ (IE latest, Chrome latest and Firefox latest, Edge latest): __mandatory__
* __Visual Studio 2019 Professional__: optional, required only for additional functions like build tasks and other non-directly related to running tests with Test Studio

## Configuring the Azure DevOps Build Pipeline

Below are listed the steps to configure the build pipeline in Azure DevOps.

### Create a new project in Azure DevOps

Start with creating a new project in Azure. The one used in this example is named _Test Studio 1_.

![Create New project][1]

### Create a Self-hosted Agent

Depending on whether tests should be running as a part of the app under test deployment to Live/Test environments or as part of daily builds there are **two types of agents**. If tests are supposed to run as a part of the release, the agent executing the tests should be registered in a Deployment group. If tests are supposed to run on demand after each build of the source code, the agent executing the tests should be registered to an Agent pool.<br><br>

The tests should be run using <a href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-windows?view=azure-devops" target="_blank">self-hosted Windows agents</a> in order to be able to use the corresponding Test Studio installation.

To create such agent, follow the steps listed below

1.&nbsp; Open the current **Project settings**.

![Open the current project settings][2]

2.&nbsp; Click on **Pipelines -> Agent Pools**.

![Agent Pools][3]

3.&nbsp; Add a new pool or open the default one.

![New Agent Pools][4]

4.&nbsp; Click **New Agent**,

![New Agent][5]

5.&nbsp; Download the Agent to the corresponding physical or virtual machine as per the installation requirements above.

6.&nbsp; Extract the Agent and run as Administrator.

![Start Agent][6]

> **Note!** In order to avoid any permissions issues, please make sure that the user configuring the Agent is part of the following Permission Groups: Build Administrators, Release Administrators, Project Administrators, **ProjectName** Team.

### Configure a Self-hosted Agent

1.&nbsp; Enter server URL: i.e. https://dev.azure.com/OrganizationName.

2.&nbsp; Create Personal Access Token (PAT) as described <a href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-windows?view=azure-devops#permissions" target="_blank">here</a> and save it.

3.&nbsp; Choose PAT for authentication type and paste yours.

4.&nbsp; Choose the Agent pool you created earlier.

5.&nbsp; Choose Agent name, the default name is the machine name on which it is hosted.

6.&nbsp; Choose a work folder or press enter for the default one _work sub-folder.

7.&nbsp; Select N when asked to enter agent as a service.

8.&nbsp; Enter configure autologon and run agent on startup Y/N is optional.

![Configure Agent][7]

9.&nbsp; Upon successful configuration the config console will close, so execute run.cmd in console to trigger the Agent.

![Trigger Agent][8]

### Run Tests on Agent

1.&nbsp; Go to **Pipelines >> Builds >> Create new**.

![Create Pipeline][9]

2.&nbsp; It is important to select **Use the classic editor** in order to create a pipeline without YAML.

![Create Pipeline][10]

3.&nbsp; Choose the repository where your code is and click **Continue**.

![Choose repo][11]

4.&nbsp; Choose **Empty job** as a template for the build

![Choose empty job][12]

5.&nbsp; Select a pipeline and choose the Agent pool configured earlier.

![Select pipeline and agent pool][13]

6.&nbsp; Create a new task on the **Agent -> Utility -> Command line**.

![Command line new task][14]

7.&nbsp; Modify the Command line script, so that it executes tests using the CLI Test Studio Runner and make sure you add the junit option to the CLI test runner in order to output the results in junit format (junit is supported by the publish results task). The script points to the location of the ArtOfTest.Runner.exe combined with the desired test or test list (see the <a href="/features/test-runners/artoftest-runner" target="_blank">syntax options here</a>). In the example below, we are executing a test list.

![Command line script][15]

8.&nbsp; Select **Continue on error** from the Command line script **Control Options**, if you’d like to complete a results' upload task (see next list point) even if the test execution task fails.

![Control Options][16]

9.&nbsp; To add a **Publish Test Result** task, select the folder to which the test results are deployed and choose to upload all .xml files **.xml for file search for example. 

![Publish Test results task][17]

Something to consider here is whether results are piled together in this folder, if that’s the case there may be a need to make sure the results folder is empty before each run. If the folder is part of the build folders managed by the Azure agent, then this is not a concern because they are recreated for each run.

![Publish Test results][18]

### Results from Test Execution

Once the test run finishes, you can see the results in the **Test** tab.

![See test results][19]

[1]: /img/advanced-topics/build-server/azure-devops/fig1.png
[2]: /img/advanced-topics/build-server/azure-devops/fig2.png
[3]: /img/advanced-topics/build-server/azure-devops/fig3.png
[4]: /img/advanced-topics/build-server/azure-devops/fig4.png
[5]: /img/advanced-topics/build-server/azure-devops/fig5.png
[6]: /img/advanced-topics/build-server/azure-devops/fig6.png
[7]: /img/advanced-topics/build-server/azure-devops/fig7.png
[8]: /img/advanced-topics/build-server/azure-devops/fig8.png
[9]: /img/advanced-topics/build-server/azure-devops/fig9.png
[10]: /img/advanced-topics/build-server/azure-devops/fig10.png
[11]: /img/advanced-topics/build-server/azure-devops/fig11.png
[12]: /img/advanced-topics/build-server/azure-devops/fig12.png
[13]: /img/advanced-topics/build-server/azure-devops/fig13.png
[14]: /img/advanced-topics/build-server/azure-devops/fig14.png
[15]: /img/advanced-topics/build-server/azure-devops/fig15.png
[16]: /img/advanced-topics/build-server/azure-devops/fig16.png
[17]: /img/advanced-topics/build-server/azure-devops/fig17.png
[18]: /img/advanced-topics/build-server/azure-devops/fig18.png
[19]: /img/advanced-topics/build-server/azure-devops/fig19.png
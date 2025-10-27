---
title: Azure DevOps Pipelines and Test Studio Tests
page_title: Test Studio Tests in Azure DevOps Build Pipelines
description: "Learn how to integrate and execute Test Studio automated tests in Azure DevOps pipelines using self-hosted or Microsoft-hosted agents. This guide covers prerequisites, agent setup, artifact management, and limitations for web and desktop test execution."
position: 0
---
# Test Studio Tests and Azure DevOps Build Pipeline

You can integrate <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests for automated execution within Azure DevOps pipelines. This article outlines the key prerequisites and configuration steps you should consider before setting up your pipeline.

## Environmental Prerequisites

The build machine may be either a physical or virtual system that hosts both the Azure DevOps agent and the Test Studio Runner. For minimum hardware and software requirements, see the <a href="/system-requirements" target="_blank">Test Studio system requirements documentation</a>.

Additional prerequisites: 

* __Azure DevOps account__ enabled to configure Agent pools, Microsoft-hosted agent VMs and pipelines: __mandatory__
* __Azure DevOps Agent __: __mandatory__
* __Test Studio Run-time Edition__ (ArtOfTest.Runner.exe must be available - preferably latest version): __mandatory__
* __Internet Browser__ (Chrome, Edge, Firefox - preferably latest versions) or WPF/desktop application: __mandatory__

## Upload the Testing Project into a Source Control Repository

Executing the Test Studio automated tests as part of any CI pipeline requires the project to be deployed on the execution machine. The most convenient approach is to manage the project into a source control repository and use it to checkout the current latest version at the time of execution. The type of source control repository to use depends on your company policies and specifics. 

## Choose the Configuration to Setup

Azure DevOps provides two options to run pipelines - on a on-premise local machine (physical or virtual) and on a container hosted by Microsoft. Depending on the configuration you choose there are different initial adjustments of the setup. 

Running __pipeline with Test Studio automated tests on a local machine__ requires you to: 

* [create a new self-hosted agent in the AzDO project](#create-a-self-hosted-agent)
* [configure the self-hosted agent to always run n interactive mode](#configure-the-self-hosted-agent)

Running __pipeline with Test Studio automated tests on a Microsoft hosted machine__ requires you to:

* [upload Test Studio installer as artifact](#add-test-studio-run-time-installer-as-artifact-in-azdo-project)
* [check known limitations for using the MS-hosted agent machines](#limitations-in-using-ms-hosted-agent-with-test-studio-tests)

    > __Important!__
    > <br>
    > <br>
    > Microsoft-hosted agent VMs use no GUI session or UI, thus it can be __used only for executing web tests__!

## Create a Self-Hosted Agent 

Test Studio application is a Windows OS based and as such you can execute the automated tests only on a Windows machine. Thus, you need to use the <a href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-windows?view=azure-devops" target="_blank">AzDO self-hosted Windows agent</a> to execute tests as part of a pipeline.

To create such agent, follow the steps listed below: 

1. Open the **Project settings** of the current AzDO project.

    ![Open the current AzDO project settings][2]

2. Click on **Pipelines -> Agent Pools**.

    ![Agent Pools][3]

3. Add a new pool or open the default one.

    ![New Agent Pools][4]

4. Click **New Agent**,

    ![New Agent][5]

5. Download the Agent to the corresponding physical or virtual machine as per the installation requirements above.

6. Extract the Agent and run as Administrator.

    ![Start Agent][6]

> **Note** 
> <br>
> To avoid any permissions issues make sure that the user configuring the Agent is part of the following Permission Groups in AzDO project: Build Administrators, Release Administrators, Project Administrators, ProjectName Team.

<br>
<div><a style="float:right" href="#choose-the-configuration-to-setup">Back to top of section</a></div>
<br>

## Configure the Self-Hosted Agent

1. Enter server URL: i.e. https://dev.azure.com/OrganizationName.

2. <a href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-windows?view=azure-devops#permissions" target="_blank">Create Personal Access Token (PAT)</a> and save it.

3. Choose PAT for authentication type and paste yours.

4. Choose the Agent pool you created earlier.

5. Choose Agent name, the default name is the machine name on which it is hosted.

6. Choose a work folder or press enter for the default `_work` sub-folder.

7. Choose to run the Agent in Interactive mode - select `N` when asked to run agent as a service.

8. Choose whether to configure autologon and run agent on startup - from Test Studio perspective this is optional and depends on the project demands.

    ![Configure Agent][7]

9. Upon successful configuration the config console gets closed. Run the `run.cmd` file in console to trigger the Agent.

    ![Trigger Agent][8]


<br>
<div><a style="float:right" href="#choose-the-configuration-to-setup">Back to top of section</a></div>
<br>







## Add Test Studio Run-time Installer as Artifact in AzDO Project

Follow the below steps to upload the Test Studio Run-time installer as artifact in the AzDO project:


1. Open the __Artifacts__ view in the Azure platform and choose the feed in which you want to add the Test Studio Run-time installer. 

    > __Tip!__
    ><br>
    > You can __download the Test Studio Run-time Edition *.msi installer file__ from your <a href="https://www.telerik.com/account/product-download?product=TESTSTUDIORUNTIME" target="_blank">Telerik account here</a>. 
   
2. Then select the __Connect to feed__ option to add an artifact in the feed. If you need further information about _Feeds in Azure DevOps_, you can visit the <a href="https://docs.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops" target="_blank">Microsoft docs page on the topic</a>.

    ![Artifacts and Feed in Azure](/img/advanced-topics/build-server/mha-testing/fig1.png)

3. Choose the __Universal Packages__ option from the list of artifacts. The instructions how to publish a package are listed on the right side of the list. It is necessary to use the Azure CLI to login and publish the installer file - you can find example commands, which need to be adjusted for your project specifics. If you need further information about __Publishing Universal Packages__, you can refer to the <a href="https://docs.microsoft.com/en-us/azure/devops/artifacts/quickstarts/universal-packages?view=azure-devops" target="_blank">Microsoft docs page on the topic</a>.

    ![Publish Universal package in Azure feed](/img/advanced-topics/build-server/mha-testing/fig2.png)

4. After the package is successfully uploaded, it is __listed as an artifact__ and can be used in the Azure pipelines for that project.

    ![Artifacts in Azure feed](/img/advanced-topics/build-server/mha-testing/fig3.png)

<br>
<div><a style="float:right" href="#choose-the-configuration-to-setup">Back to top of section</a></div>
<br>

## Limitations in Using MS-Hosted Agent with Test Studio Tests

* __Only web tests using Edge and Chrome browsers (both headless and headdull)__ can be executed in a Microsoft-hosted agent.
* __The <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">images on failure</a>__ are not available in the results generated from the test runs in Microsoft-hosted agent.

<br>
<div><a style="float:right" href="#choose-the-configuration-to-setup">Back to top of section</a></div>
<br>

## Continue to Setting Up a Pipeline

You can integrate the Test Studio automated tests execution in both classic and YAML type of pipelines in AzDO. Find reference for the different options and choose the one which suits your project needs: 

- Configure classic pipeline to execute tests on self hosted machine
- Configure classic pipeline to execute tests on Microsoft hosted machine
- Configure YAML pipeline to execute tests on self hosted machine
- Configure YAML pipeline to execute tests on Microsoft hosted machine

[2]: /img/advanced-topics/build-server/azure-devops/fig2.png
[3]: /img/advanced-topics/build-server/azure-devops/fig3.png
[4]: /img/advanced-topics/build-server/azure-devops/fig4.png
[5]: /img/advanced-topics/build-server/azure-devops/fig5.png
[6]: /img/advanced-topics/build-server/azure-devops/fig6.png
[7]: /img/advanced-topics/build-server/azure-devops/fig7.png
[8]: /img/advanced-topics/build-server/azure-devops/fig8.png
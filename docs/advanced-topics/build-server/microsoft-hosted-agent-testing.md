---
title: Microsoft-Hosted Agent Testing
page_title: Use  Microsoft-Hosted Agent for Test Studio Test Execution
description: "Azure DevOps pipelines with Microsoft-Hosted Agents can execute Test Studio tests in headless mode. Execute Test Studio tests in Azure pipeline with Microsoft-Hosted Agents. Headless test execution of Test Studio tests in Azure DevOps pipeline."
position: 9
---

# Test Studio Tests in Azure DevOps CI with Microsoft-Hosted Agent

Test Studio test lists can be executed in Chrome Headless mode within a Microsoft-hosted agent. This article guide you trough the process of setting up the Azure pipeline to run in a Microsoft-hosted agent.

## Environmental Prerequisites

The prerequisites from Test Studio and Azure DevOps side are listed below. Make sure that you comply with them, before proceeding with the next steps.

* Azure DevOps account enabled to configure Microsoft-hosted agent VMs with latest Chrome version.
* Active <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-Time</a> license and .msi installer for it. The minimum version of Test Studio is 2021 R3.

## Disclaimer

Executing tests in a Microsoft-hosted agent has its specifics and limitations. It is better to know about them before you proceed.

* Tests in a Microsoft-hosted agent can be __executed only in Headless browser mode__, because the container does not have UI. This is the <a href="/automated-tests/headless/headless-test-execution" target="_blank">Chrome Headless browser type</a> in Test Studio.
* The <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">images on failure</a> are not available in the results generated from the test runs in Microsoft-hosted agent.

## What is Microsoft-Hosted Agent

The Azure pipelines can be configured to run their tasks with different type of agents. The <a href="https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml" target="_blank">Microsoft-hosted agent</a> is one of these options - this is a VM created in the pipeline run-time and is based on OS image granted in Azure DevOps by Microsoft. The running VM has the Azure agent, which gets automatically connected to the Agent pool in the Azure project, latest Chrome and Edge browsers, Visual Studio and other tools, all set to run as Administrator by default. The management of this OS image is supported by the Microsoft Azure DevOps team and they commit it will be updated once per week.

> __Note__
> <br>
> <br>
> Microsoft-hosted agent VMs use no GUI session or UI. Therefore it can be __used only for headless browser testing__ supported from Test Studio for the Chrome browser.

## Setup Azure Pipeline to Execute Headless Tests on Microsoft-hosted Agent

Running Test Studio tests requires installation of the <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-time edition</a> - this is a __separate product package dedicated for test execution__ only. One license for the Run-time edition is distributed with the Test Studio Ultimate bundle and, alternatively, it can be <a href="https://www.telerik.com/purchase/teststudio" target="_blank">purchased</a> separately.

Once you have an active Test Studio Run-time license, you can __download its *.msi installer__ from your <a href="https://www.telerik.com/account/product-download?product=TESTSTUDIORUNTIME" target="_blank">Telerik account here</a> and add it in the Azure Pipeline as an _Artifact_ related to the Azure project. That way it will be available for deployment on the Microsoft-hosted agent, when this is created.

### Add Run-time Installer as Artifact

Open the __Artifacts__ view in the Azure platform and choose the feed in which you want to add the Test Studio Run-time installer. Then select the __Connect to feed__ option to add an artifact in the feed. If you need further information about _Feeds in Azure DevOps_, you can visit the <a href="https://docs.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops" target="_blank">Microsoft docs page on the topic</a>.

![Artifacts and Feed in Azure](/img/advanced-topics/build-server/mha-testing/fig1.png)

Choose the __Universal Packages__ option from the list of artifacts. The instructions how to publish a package are listed on the right side of the list. It is necessary to use the Azure CLI to login and publish the installer file - you can find example commands, which need to be adjusted for your project specifics. If you need further information about _Publishing Universal Packages_, you can visit the <a href="https://docs.microsoft.com/en-us/azure/devops/artifacts/quickstarts/universal-packages?view=azure-devops" target="_blank">Microsoft docs page on the topic</a>.

![Publish Universal package in Azure feed](/img/advanced-topics/build-server/mha-testing/fig2.png)

After the package is successfully uploaded, it is __listed as an artifact__ and can be used in the Azure pipelines for that project.

![Artifacts in Azure feed](/img/advanced-topics/build-server/mha-testing/fig3.png)

### Create a Free Form Pipeline

To create the Azure Pipeline, which will run tests in the MHA, you can start with the __classic editor__.

![Pipeline classic editor](/img/advanced-topics/build-server/mha-testing/fig4.png)

Choose the repository from which the Test Studio project will be deployed to the Microsoft-hosted agent machine. In this example I used the Azure Git repository. Be sure to use <a href="/automated-tests/headless/headless-test-execution#execute-tests-in-test-lists-using-headless-chrome-browser" target="_blank">test lists, which are set to use the Chrome browser in headless mode</a> for this pipeline test runs.

![Choose Test Studio project repository](/img/advanced-topics/build-server/mha-testing/fig5.png)

When the source location is defined, choose the __Empty pipeline__ template and __Apply__ to the pipeline.

![Empty pipeline](/img/advanced-topics/build-server/mha-testing/fig6.png)

### Set the Pipeline to Use the Microsoft-hosted Agent Pool

Once the pipeline is created, you can change its name and set the __Agent Pool__ to be used. For Microsoft-hosted agent you need to choose the __Azure Pipelines__ pool. When this option is selected, you can select a default image to be installed on the VM when running the pipeline.

![Azure pipelines Agent Pool and default agent specification](/img/advanced-topics/build-server/mha-testing/fig7.png)

### Download and Install the Test Studio Run-time on Microsoft-hosted Agent

You can use the __Universal Package__ task to download the Test Studio Run-time installer artifact.

![Universal Package task](/img/advanced-topics/build-server/mha-testing/fig8.png)

Ensure to list the feed, name and version of the artifact as you have entered these when publishing the package.

![Download Universal Package task](/img/advanced-topics/build-server/mha-testing/fig9.png)

To trigger the installation of the downloaded package, add the next task and choose the __Command Line__ option.

![Command Line task](/img/advanced-topics/build-server/mha-testing/fig10.png)

The installation can be triggered with a <a href="https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/msiexec" target="_blank">msiexec command</a> in passive mode due to the lack of UI session. Find below an example command to use in the task.

```
msiexec.exe /i c:\TestStudio_Runtime_2021_3_1103_1.msi /passive /le c:\errorlog.txt
```

### Execute the Tests on Microsoft-hosted Agent

The next task in the pipeline can be set to execute the tests. To trigger the test list run, you can again use a __Command Line__ task. In it you can list a command using the <a href="/features/test-runners/artoftest-runner" target="_blank">options of the Test Studio CLI runner</a> called __ArtOfTest.Runner.exe__.

The example in the screenshot uses the options to set custom name for the result file and to generate _junit_ formatted result for the run. In this command I use the __$(Build.Repository.LocalPath) variable provided from Azure__. It is recommended to use such environmental variables as hard-coded paths may cause some false failures.

![Test list run command](/img/advanced-topics/build-server/mha-testing/fig11.png)

Another important setting for this task is to change its __Control Options__ to __"Continue on error"__. This way the test result publish tasks will get executed regardless of the test execution outcome.

### Publish Results Generated on Microsoft-hosted Agent

It is useful to publish both the Test Studio results file and the _junit_ formatted file. These require setup of separate tasks. 

Create a __Publish Pipeline Artifact__ task to upload the Test Studio results file as an artifact in the pipeline.

![Publish Pipeline Artifact task](/img/advanced-topics/build-server/mha-testing/fig12.png)

The _junit_ formatted results can be published to the pipeline build summary with the __Publish Test Results__ task.

![Publish Test results task](/img/advanced-topics/build-server/mha-testing/fig13.png)

For both these tasks you can use the variable __$(Build.Repository.LocalPath)__.

## Run the Azure Pipeline

With the pipeline set in this way, you can trigger the Test Studio headless test execution on a Microsoft-hosted agent VM.

![Run the pipeline](/img/advanced-topics/build-server/mha-testing/fig14.png)

In the __Run Summary__ you can find useful details for the run and access the Test Studio result file for download.

![Summary of the run](/img/advanced-topics/build-server/mha-testing/fig15.png)

In the __Tests__ section you can see a summary of the test results based on the _junit_ formatted results.

![Tests results of the run](/img/advanced-topics/build-server/mha-testing/fig16.png)
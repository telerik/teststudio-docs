---
title: Azure Results Sync
page_title: Azure Results Sync
description: "Learn how to use Telerik.TestStudio.AzureTestPlansMapper.exe to create mappings between Test Studio tests and AzureDevOps test cases."
position: 2
---

# Azure Results Sync

**Telerik.TestStudio.AzureResultsSync.exe** is a CLI tool that converts Test Studio test results to AzureDevOps test results and uploads these results as a new AzureDevOps run.

# How to use the tool

1. Run a Test Studio list and specify where rusults to be output.

1. Run **Telerik.TestStudio.AzureResultsSync.exe**. 
	- Use **url** parameter to specify you AzureDevOps organization. For example: https://dev.azure.com/my-org
    - Use **map** parameter to specify the abolute path to your mapping file.
    - Use **aiiresult** parameter to specify the abolute path to your Test Studio result file.
    - Use **token** parameter to specify your personal access token (PAT). If **token** param is missing the tool will try to read the value from **TSAzureToken** environment variable. 


# Local Machine Example

Telerik.TestStudio.AzureResultsMapper.exe url=https://dev.azure.com/my-org token=<MY-TOKEN> map="<PATH-MAPPING-FILE>" aiiresult="<PATH-MAPPING-FILE>"

# AzureDevOps Example

```
jobs:
  - job: Run and Upload Results
    steps:
      - task: CmdLine@2
        displayName: Run Test Studio tests
        continueOnError: true
        inputs:
          script: |
             "c:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" list="$(System.DefaultWorkingDirectory)\TestingProjects\HTMLProject\MapperPipeline\TestLists\mixed list.aiilist" result=myResult

      - task: CmdLine@2
        displayName: Upload results
        condition: always()
        env:
          TSAzureToken: $(System.AccessToken)
        inputs:
          script: |
            "c:\Program Files (x86)\Progress\Test Studio\Bin\AzureResultsMapper\Telerik.TestStudio.AzureResultsSync.exe" url=https://dev.azure.com/prgs-devtools map=$(System.DefaultWorkingDirectory)\TestingProjects\HTMLProject\MapperPipeline\AzDoMap.tsazdo aiiresult=$(System.DefaultWorkingDirectory)\TestingProjects\HTMLProject\MapperPipeline\Results\myResult.aiiresult

```

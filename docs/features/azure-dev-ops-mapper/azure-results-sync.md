---
title: Azure Results Sync
page_title: Azure Results Sync
description: "Learn how to use Telerik.TestStudio.AzureTestPlansMapper.exe to create mappings between Test Studio tests and Azure DevOps test cases."
position: 3
---

# Azure Results Sync

**Telerik.TestStudio.AzureResultsSync.exe** is a CLI tool that converts Test Studio test results to Azure DevOps test results and uploads these as a new Azure DevOps run.

# How to Use the Tool

1. Run a Test Studio test list and specify where to output the results. 

  - The run can be initiated using the <a href="/features/test-runners/artoftest-runner" target="_blank">CLI runner ArtOfTest.Runner.exe</a>. 
  - Or through the project option <a href="/automated-tests/test-lists/test-list-execution#execute-test-list-locally" target="_blank">__'Run List'__</a> which outputs the results in the project sub-folder __'Results'__. 

1. Use command prompt to run **Telerik.TestStudio.AzureResultsSync.exe**. 

	- Use **url** parameter to specify the Azure DevOps organization. </br>
    __For example:__ https://dev.azure.com/my-org
  - Use **map** parameter to specify the absolute path to the mapping file generated from the mapper tool.
  - Use **aiiresult** parameter to specify the absolute path to the Test Studio test list results file.
  - Use **token** parameter to specify your personal access token (PAT). </br>
    __Note:__ If **token** param is missing the tool tries to read the value from **TSAzureToken** environment variable. 


# Local Machine Example

```cmd 
"c:\Program Files (x86)\Progress\Test Studio\Bin\AzureResultsMapper\Telerik.TestStudio.AzureResultsSync.exe" url=https://dev.azure.com/my-org token=<MY-TOKEN> map="<PATH-MAPPING-FILE>" aiiresult="<PATH-MAPPING-FILE>"
```

# Azure DevOps Example

In the scenario of building a CI pipeline the test list run needs to be set through the Test Studio CLI runner ArtOfTest.Runner.exe with specifying where to output the result. Check <a href="/advanced-topics/build-server/azure-devops" target="_blank">here how to implement the test list execution in Azure DevOps pipeline</a>. Next comess the call to the mapper tool which defines where the results to be uploaded. 

Below is an example pipeline with only these two jobs:

```yml
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

- The __'Run Test Studio tests'__ task executes a test list with the ArtOfTest.Runner.exe and stores the results in file named myResult.aiiresult.
- The __'Upload results'__ task converts the Test Studio results from myResult.aiiresult file and uploads them as new Azure DevOps run. 
- The __'Upload results'__ task is configured to be executed always - "condition: always()". This way, even if the test execution from the previous step fails, the results get uploaded.
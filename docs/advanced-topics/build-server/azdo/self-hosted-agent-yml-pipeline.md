---
title: AzDO YAML Pipeline Using Self Hosted Agent 
page_title: Test Studio Tests in Azure DevOps YAML Pipeline Using Self-Hosted Agent
description: "Integrate Test Studio tests in Azure DevOps continuous integration. Execute Test Studio tests with Azure DevOps YAML Pipeline configured with Self Hosted agent."
position: 3
---
# Test Studio Tests in Azure DevOps YAML Pipeline Using Self-Hosted Agent

<a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests can be successfully integrated for execution with the Azure DevOps pipelines. 

Below is a sample YAML pipeline using self-hosted agent machine which follows the instructions for <a href="/advanced-topics/build-server/azdo/self-hosted-agent-classic-pipeline#add-command-line-agent-task-to-execute-test-or-test-list" target="_blank">building the classic pipeline using self-hosted agent</a>.

```YAML
trigger:
- main

pool: 
 name: selfHostedAgentPool

steps: 

# Specify test list to execute
- script: |
    "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" ^
      list="$(System.DefaultWorkingDirectory)\navToTSPage\TestLists\openTSPage.aiilist" ^
      result="openTSPage" ^
      settings="$(System.DefaultWorkingDirectory)\navToTSPage\local-run-settings-using-ff.json" ^
      junit
  displayName: 'CMD Execute Test List'
  continueOnError: true

# Publish JUnit result
- task: PublishTestResults@2 
  displayName: 'Publish Test Results **.xml' 
  condition: succeededOrFailed()
  inputs: 
    testResultsFiles: '**/*.xml' 
    searchFolder: '$(System.DefaultWorkingDirectory)\navToTSPage\Results' 
    failTaskOnFailedTests: true
    testRunTitle: 'Test Run - openTSPage'

# Publish aiiresult file
- task: PublishPipelineArtifact@1
  displayName: 'Publish aiiresult file'
  condition: succeededOrFailed()
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage.aiiresult'
    artifact: 'aiiresult - openTSPage'

# Check if failure details exists 
- script: |
    if exist "$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage_files" (
      echo "##vso[task.setvariable variable=folderExists]true"
    ) else (
      echo "##vso[task.setvariable variable=folderExists]false"
    )
  displayName: 'Check if failure details folder exists'

# Publish failure details if applicable
- task: PublishPipelineArtifact@1
  displayName: 'Publish failure details if applicable'
  condition: and(succeededOrFailed(), eq(variables['folderExists'], 'true'))
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage_files'
    artifact: 'failure-details - openTSPage'
```
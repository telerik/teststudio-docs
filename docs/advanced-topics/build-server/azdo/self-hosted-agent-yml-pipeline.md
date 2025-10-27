---
title: Azure YAML Pipeline Using Self Hosted Agent 
page_title: Test Studio Tests in Azure DevOps Build Pipelines - YAML Pipeline Using Self Hosted Agent
description: "Integrate Test Studio tests in Azure DevOps continuous integration. Execute Test Studio tests with Azure DevOps YAML Pipeline configured with Self Hosted agent."
position: 3
---
# Test Studio Tests in Azure DevOps Build Pipelines - YAML Pipeline Using Self Hosted Agent

```YAML
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

trigger:
- main

pool: 
 name: selfHostedAgentPool

steps: 

- script: |
    "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" ^
      list="$(System.DefaultWorkingDirectory)\navToTSPage\TestLists\openTSPage.aiilist" ^
      result="openTSPage" ^
      settings="$(System.DefaultWorkingDirectory)\navToTSPage\local-run-settings-using-ff.json" ^
      junit
  displayName: 'CMD Execute Test List'
  continueOnError: true

- task: PublishTestResults@2 
  displayName: 'Publish Test Results **.xml' 
  condition: succeededOrFailed()
  inputs: 
    testResultsFiles: '**/*.xml' 
    searchFolder: '$(System.DefaultWorkingDirectory)\navToTSPage\Results' 
    failTaskOnFailedTests: true
    testRunTitle: 'Test Run - openTSPage'

- task: PublishPipelineArtifact@1
  displayName: 'Publish aiiresult file'
  condition: succeededOrFailed()
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage.aiiresult'
    artifact: 'aiiresult - openTSPage'

- script: |
    if exist "$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage_files" (
      echo "##vso[task.setvariable variable=folderExists]true"
    ) else (
      echo "##vso[task.setvariable variable=folderExists]false"
    )
  displayName: 'Check if failure details folder exists'

- task: PublishPipelineArtifact@1
  displayName: 'Publish failure details if applicable'
  condition: and(succeededOrFailed(), eq(variables['folderExists'], 'true'))
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage_files'
    artifact: 'failure-details - openTSPage'
```
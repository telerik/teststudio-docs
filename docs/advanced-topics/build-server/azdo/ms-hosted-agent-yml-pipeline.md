---
title: AzDO YAML Pipeline Using MS-Hosted Agent 
page_title: Test Studio Tests in Azure DevOps YAML Pipeline Using Microsoft-Hosted Agent
description: "Integrate Test Studio tests in Azure DevOps continuous integration. Execute Test Studio tests with Azure DevOps YAML Pipeline configured with MS-Hosted agent."
position: 4
---
# Test Studio Tests in Azure DevOps YAML Pipeline Using Microsoft-Hosted Agent

<a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests can be successfully integrated for execution with the Azure DevOps pipelines. 

Below is a sample YAML pipeline using Microsoft-hosted agent machine which follows the instructions for <a href="/advanced-topics/build-server/azdo/ms-hosted-agent-classic-pipeline#add-universal-download-package-task-to-deploy-test-studio-installer-on-agent-machine" target="_blank">building the classic pipeline using MS-hosted agent</a>. 


```YAML
trigger:
- none

pool:
  vmImage: 'windows-latest'

steps:

# Download latest runtime from feed
- task: DownloadPackage@1
  inputs:
    packageType: 'upack'
    feed: '/b1db09af-8756-4092-9ea2-df51da8b1e16'
    view: 'eaa25bb8-bcde-44dd-8bd5-0fbedb0a137e'
    definition: '791755a9-0985-4fe9-8905-eea8f0a03569'
    version: '0.0.3'
    downloadPath: '$(Pipeline.Workspace)\downloads'

# Install latest runtime
- task: PowerShell@2
  displayName: Install runtime
  inputs:
      targetType: 'inline'
      script: |
        $temp_dir = "$(Pipeline.Workspace)\downloads"
        # Select the installer from the temp folder.
        $installer = (Get-ChildItem $temp_dir -recurse -include TestStudio_Runtime_*.msi | Sort-Object LastWriteTime | Select-Object -last 1)
        
        # Output the installer file name that is installed
        Write-Output("Msi to install: " + $installer.name)
        
        # Install Test Studio silently in temp folder.
        $arg = @()
        $arg += "/i"
        $arg += ("$(Pipeline.Workspace)\downloads\" + $installer.name)
        $arg += "/passive"
        Write-Host "Calling msiexec.exe" $arg
        Start-Process "msiexec.exe" -ArgumentList $arg -Wait
        Write-Output("Install completed!")

# Specify test list to execute
- script: | 
    "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" ^
      list="$(System.DefaultWorkingDirectory)\navToTSPage\TestLists\openTSPage.aiilist" ^
      result="openTSPage" ^
      settings="$(System.DefaultWorkingDirectory)\navToTSPage\mshosted-run-settings-using-edge-headless.json" ^
      junit
  displayName: 'CMD Execute Test List'
  continueOnError: true

# Publish JUnit result
- task: PublishTestResults@2 
  displayName: 'Publish Test Results **.xml' 
  inputs: 
    testResultsFiles: '**.xml' 
    searchFolder: '$(System.DefaultWorkingDirectory)\navToTSPage\Results' 
    failTaskOnFailedTests: true
    testRunTitle: 'Test Run - openTSPage'

# Publish aiiresult file
- task: PublishPipelineArtifact@1
  displayName: 'Publish aiiresult file'
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage.aiiresult'
    artifact: 'aiiresult file - openTSPage'

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
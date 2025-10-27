---
title: Azure YAML Pipeline Using MS-Hosted Agent 
page_title: Test Studio Tests in Azure DevOps Build Pipelines - YAML Pipeline Using MS-Hosted Agent
description: "Integrate Test Studio tests in Azure DevOps continuous integration. Execute Test Studio tests with Azure DevOps YAML Pipeline configured with MS-Hosted agent."
position: 4
---
# Test Studio Tests in Azure DevOps Build Pipelines - YAML Pipeline Using MS-Hosted Agent


```YAML
trigger:
- none

pool:
  vmImage: 'windows-2019'

steps:

# Download latest runtime from feed
- task: DownloadPackage@1
  inputs:
    packageType: 'upack'
    feed: '/b1db09af-e0c4-4092-9ea2-df51da8b1e16'
    view: 'eaa25bb8-0c40-44dd-8bd5-0fbedb0a137e'
    definition: '791755a9-fc77-4fe9-8905-eea8f0a03569'
    version: '0.0.3'
    downloadPath: '$(Pipeline.Workspace)\downloads'
    
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

- script: | 
    "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" ^
      list="$(System.DefaultWorkingDirectory)\navToTSPage\TestLists\openTSPage.aiilist" ^
      result="openTSPage" ^
      settings="$(System.DefaultWorkingDirectory)\navToTSPage\mshosted-run-settings-using-edge-headless.json" ^
      junit
  displayName: 'CMD Execute Test List'
  continueOnError: true

- task: PublishTestResults@2 
  displayName: 'Publish Test Results **.xml' 
  inputs: 
    testResultsFiles: '**.xml' 
    searchFolder: '$(System.DefaultWorkingDirectory)\navToTSPage\Results' 
    failTaskOnFailedTests: true
    testRunTitle: 'Test Run - openTSPage'

- task: PublishPipelineArtifact@1
  displayName: 'Publish aiiresult file'
  inputs:
    targetPath: '$(System.DefaultWorkingDirectory)\navToTSPage\Results\openTSPage.aiiresult'
    artifact: 'aiiresult file - openTSPage'

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
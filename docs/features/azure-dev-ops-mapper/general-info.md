---
title: General information about Azure DevOps Mapper
page_title: General information about Azure DevOps Mapper
description: "Learn how to map Test Studio tests to Azure DevOps test cases and how to sync resutls."
position: 1
---

# Overview

Test Studio provides a mechanism to integrate with Azure DevOps test plans and upload results as Azure DevOps test run.

To achieve the integration you will have to create a mapping between Test Studio tests and Azure DevOps test cases. Later after you have executed a Test Studio test list you can fetch the test results, convert them to Azure DevOps test case results and create a new Azure DevOps run.


## Azure Test Plans Mapper

**Telerik.TestStudio.AzureTestPlansMapper.exe** is GUI tool that allows you to map Test Studio test from a particular project to predefined Azure DevOps test cases. The tool is located in **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureTestCaseMapper** folder. Find [here detailed instructions on how to create a mapping file](/features/azure-dev-ops-mapper/azure-test-plans-mapper). 


## Azure Results Sync

**Telerik.TestStudio.AzureResultsSync.exe** is a CLI tool that converts Test Studio test results to Azure DevOps test results and uploads these as a new Azure DevOps run. The tool is located in **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureResultsMapper** folder and is designed to be used in a CI/CD pipeline. Find the [detailed instructions on its options here](/features/azure-dev-ops-mapper/azure-results-sync).

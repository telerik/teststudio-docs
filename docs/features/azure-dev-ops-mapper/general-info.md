---
title: General information about AzureDevOps mapper
page_title: General information about AzureDevOps mapper
description: "Learn how to map Test Studio tests to AzureDevOps test cases and how to sync resutls."
position: 1
---

# Overview

Test Studio provides a mechanism to integrate with AzureDevOps test plans and upload results as AzureDevOps test run.

To achieve the ingration you will have to create a mapping between Test Studio tests and AzureDevOps test cases. Later after you have executed a Test Studio test list you can fetch the test results, convert them to AzureDevOps test case results and create a new AzureDevOps run.


## Azure Test Plans Mapper

**Telerik.TestStudio.AzureTestPlansMapper.exe** is GUI tool that allows you to map Test Studio test from a particular project to predefined AzureDevOps test cases. The tool is located in **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureTestCaseMapper** folder. For more information on how to create a mapping file check this (article)[/docs/features/azure-test-plans-mapper]. 


## Azure Results Sync

**Telerik.TestStudio.AzureResultsSync.exe** is a CLI tool that converts Test Studio test results to AzureDevOps test results and uploads these results as a new AzureDevOps run. The is located in **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureResultsMapper** folder and is designed to be used in a CI/CD pipeline. For more information on how to use it check this (arctcle)[/docs/features/azure-results-sync].

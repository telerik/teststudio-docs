---
title: Missing API Assembly Files
page_title: APITesting Framework solution
description: How to resolve error missing assembly for APITesting Framework. Error "Could not load file or assembly Telerik.ApiTesting.Framework. The system cannot find the file specified". Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=xxxx.x.xxx.xxxx, Culture=neutral, PublicKeyToken=xxx' or one of its dependencies. The system cannot find the file specified.
position: 1
---
# Resolve a Missing API Assembly Files Error

## Problem

If you have an embedded <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">API test as step</a>, which has a code behind file, you might encounter similar error after updating Test Studio:

```
Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=xxxx.x.xxx.xxxx, Culture=neutral, PublicKeyToken=xxx' or one of its dependencies. The system cannot find the file specified.
```

This means that the API embeded project was build with the previous version of APITesting Framework and it generated the project *dll* files. You need to rebuild it with the latest version of the framework.

## Solution

To fix the project execution, you need to delete the mentioned assembly files in the **bin** folder of the embedded API project. It is located in the **ApiTests** subfolder under the project root folder, like **C:\MyTestStudioProject\ApiTests\bin**. This will ensure that the API project will be rebuilt with the new Telerik.APITesting.Framwork assembly and it should work as before the update.

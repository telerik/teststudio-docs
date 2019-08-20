---
title: Missing API Assembly Files
page_title: APITesting Framework solution
description: How to resolve error missing assembly for APITesting Framework. Error "Could not load file or assembly Telerik.ApiTesting.Framework. The system cannot find the file specified".
position: 1
---
# Resolve a Missing API Assembly Files Error

## Problem

After updating Test Studio you might encounter similar error:

**Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=2018.3.927.1751, Culture=neutral, PublicKeyToken=5a31053920bb0a73' or one of its dependencies. The system cannot find the file specified.**

This means the you have an embedded <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">API test as step</a> is not successfully built during execution. Since this project has a code behind file, it generates an assembly *dll* file, which was already built with the previous version.

## Solution

You need to delete the mentioned assembly files in the **bin** folder of the embedded API project. It is located in the **ApiTests** subfolder under the project root folder, like **C:\MyTestStudioProject\ApiTests\bin**. This will ensure that the API project will be rebuilt with the new Telerik.APITesting.Framwork assembly and it should work as before the update.

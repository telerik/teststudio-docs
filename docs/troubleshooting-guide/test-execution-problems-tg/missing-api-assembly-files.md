---
title: Missing API Assembly Files
page_title: API Testing Framework solution
description: How to resolve error missing assembly for API Testing Framework. Error "Could not load file or assembly Telerik.ApiTesting.Framework. The system cannot find the file specified". Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=xxxx.x.xxx.xxxx, Culture=neutral, PublicKeyToken=xxx' or one of its dependencies. The system cannot find the file specified.
position: 1
---
# Resolve a Missing API Assembly Files Error

## Problem

If you have an embedded <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">API test as step</a>, which has a code behind file, you might encounter similar error after updating Test Studio:

````
Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=xxxx.x.xxx.xxxx, Culture=neutral, PublicKeyToken=xxx' or one of its dependencies. The system cannot find the file specified.
````

This means that the API embeded project was built with the previous version of APITesting Framework and the *dll* files were generated with that version. 

## Solution

To fix this error, you need to rebuild the project with the latest installed version of the framework. To do that, delete the mentioned assembly files in the **bin** folder of the embedded API project. It is located in the **ApiTests** subfolder under the project root folder, like **C:\MyTestStudioProject\ApiTests\bin**. That way the API project will be rebuilt with the new Telerik.APITesting.Framwork assembly and resolve the error occurance.

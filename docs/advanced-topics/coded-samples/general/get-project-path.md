---
title: Get Project Path
page_title: Get Project Path
description: "Get Project root Path in Test Studio coded test."
position: 1
---
# Get Current Test Project Path

*I would like to get the path (in the context of the file system) to which the current test project belongs.*

## Solution

This is doable with a coded solution. Create a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> inside of a test:

````C#
this.ExecutionContext.DeploymentDirectory;
````
````VB
Me.ExecutionContext.DeploymentDirectory
````

![Current path][1]

This will store the current project path inside the string variable *currentProjectFolder*. The actual path string can be, for example:

* **C:\Users\smith\Documents\Test Studio Projects\TestProject1**

However, when running tests from the Visual Studio <a href="/getting-started/test-execution/vs-2012-test-explorer" target="_blank">Test Explorer</a>, the above code will return a complex Out folder and not the Project's containing folder. For instance:

* **C:\MySampleProject\TestResults\smith_Smith 2011-11-21 12_56_51\Out**

You might also want to get the path of the data source files attached to your test project. When a project contains a data source, it's stored in **Project Folder\Data**. For instance, your test might be data bound to an Excel file by the name of **excelSample.xlsx**. This file will be stored under **Project Folder\Data\excelSample.xlsx**. Here's how to get this path in code:

````C#
string dataSourcePath = this.ExecutionContext.DeploymentDirectory + @"\Data\excelSample.xlsx";
````
````VB
Dim dataSourcePath As String = Me.ExecutionContext.DeploymentDirectory + "\Data\excelSample.xlsx"
````

It's still possible to edit or replace it from that location in a coded step. This will work even if the test is data bound to the file in question. 

[1]: /img/advanced-topics/coded-samples/general/get-project-path/fig1.png

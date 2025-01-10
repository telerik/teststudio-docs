---
title: Variables
page_title: Variables
description: "Progress® Test Studio® for APIs - Variables"
position: 0
published: true
---

# Variables

## Overview

Test Studio for APIs introduces Variables as a new concept in the Test Studio product family. The Variables are named values that can be persisted in the project files (**Design-time Variables**) or dynamically created by Test Steps during their execution (**Runtime Variables**).

The values of Runtime Variables exist only during the Project execution and are not persisted in the main Project files. (Test Studio for APIs creates a temporary folder named ".variables" where Runtime Variables are temporary stored - see [Runtime Variables](#Runtime-Variables) below for more information.). The Values of Runtime Variables have precedence over the Design-time Variables with the same name on the same Level.

Variables can be **Test-level** and **Project-level**. The Project-level Variables are accessible by all Tests, while the Test-level Variables are accessible only to the corresponding Test. 

> Use the -v command line argument to override Project-level Variables when executing tests from command prompt - e.g:
> `Telerik.ApiTesting.Runner.exe test -p "demotests" -v base-url=http://localhost:5000`

A Project-level Variable will not be accessible to Tests that define a Test-level variable with the same name. All Steps in a Test have access to the same Variables.

> To share a Test-level Variable with other Tests, use a Set Variable Step and choose Level = Project.


## Referencing Variables

The syntax for referencing a Variable Value is:

```
{%raw%}{{variable-name}}{%endraw%}
```

The Value of a Variable can contain references to other Variables, for example variable named "base-url" could have a value like:

```
{%raw%}{{protocol}}://{{host}}:{{port}}{%endraw%}
```

![Nesting Variables][3]

The Runtime will replace the references with the corresponding values when executing the Project.

Many Test Step properties allow variable references, for example you could use Variables in the HTTP Request Step's Method, Url, Body and Headers (both in Name and Value) properties.


## Variable Precedence

When a reference to a variable is used, the reference itself does not specify if the value should be taken from Test-level or Project-level. When the variable is being resolved, the Progress® Test Studio® for APIs Runtime will always look for the variable first on a Test-level and if it is not found - it will look for it on a Project-Level. If a Runtime Variable and a Design-time Variable exist on the same level - the Runtime Variable will be used. 

In summary - the following precedence is used:

1. Test-level Runtime Variable
2. Test-level Design-time Variable
3. Project-level Runtime Variable
4. Project-level Design-time Variable

## Runtime Variables

Some Test Steps create Runtime Variables:

- HTTP Request Step - When an HTTP Response is received, the Step will create the following Test-level Variables: StatusCode, Body, Headers, ReasonPhrase, ExecutionTime 
- Set Variable - Creates a Variable with the specified name on Test or Project Level. The Variable Value is taken from another Runtime or Design-time Variable.


> The Runtime Variables are visible (read-only) in the Variables Pane after execution.

Test Studio for APIs stores Runtime Variables in a temporary folder named ".variables" in the root of the test project. Files in the ".variables" folder are related to the last test run and are overwritten on every execution so it is not recommended to include them in your source control. 

> Every time the a project is closed, all files in the ".variables" folder are deleted.

 If you need to clear all Runtime Variables without closing the project (for example if you are debugging your tests and need to execute a single test case or step, without having any left-over runtime variables), you can use the "**Clear All Runtime Variables**" button in the Variables pane.

![Clear All Runtime Variables][4]


## Creating Design-time Variables

Use the Variables Pane to create Design-time Variables in the Test that is selected in the Project Explorer, or in the Project itself.

> The Project Variables whose Values are overridden by Test Variables will appear with strikethrough effect.

![Variables Pane][1]

## Accessing Variables

Progress® Test Studio® for APIs makes it easy to access project and test variables by automatically populating the `Source` variable field.

![Source Variable Field][2] 

> Conditions cannot access variables that are created by the step during runtime because the condition is executed prior to the step. Verifications on the other hand have access to those variables.

## Use Cases for Variables

Project-level Design-time Variables:

- Base Url for your REST API
- Static Authentication Token or Username/Password


Project-level Runtime Variables

- Dynamic Authentication Token (retrieved from token issuer)
- Common data used by several tests 


Variables from the CLI arguments:

- Override environment-specific Project-level Variables.



[1]: /img/features/variables-pane.png
[2]: /img/features/accessing-variables.png
[3]: /img/features/nesting-variables.png
[4]: /img/features/clear-all-runtime-variables.png






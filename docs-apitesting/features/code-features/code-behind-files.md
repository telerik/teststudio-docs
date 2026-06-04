---
title: Code-Behind Files
page_title: Code-Behind Files
description: "Progress® Test Studio® for APIs - Code Features - Code-Behind Files"
position: 2
published: true
---

# Code-Behind Files

Each test case in Progress® Test Studio® for APIs can have a corresponding code-behind file. The code-behind file will be automatically added when a [coded step](./coded-steps) is added to the test or you can explicitly create it with the "*Add Code-Behind*" option in the test's context menu in the project explorer.

![Add Code-Behind File][1]

If this is the first time you are adding a code-behind file to this project, you will be prompted to select a [coding language for the project](./project-coding-language) (C# or Visual Basic).

Code-behind files are generated with a default empty test method where you can implement your custom code. You can rename this method, if preferred, or delete it and add your custom test methods. Each code behind class can contain multiple test methods.

![Add Code-Behind File][2]

See the [Coded Steps](./coded-steps) article which describes how to execute the code in a test method. In order to be able to execute a test method from a coded step, the methods need to be defined as **public** and **should require no parameters**. One test method can be referenced by more than one coded step.

## Multiple Classes in a Code-Behind File

You can also implement multiple test classes in a single code-behind file but only one of them can be associated to a test case and its methods be directly executed by the test's coded steps. Any additional classes in the code-behind file can be referenced by the primary class, but their methods cannot be directly executed by coded steps.

## Map Test Case to Code-Behind Class

When a code-behind file is added to a test, the default class is associated to the test (via the test's "*ClassName*" property). The new class will be named according to the name of the test case, but empty spaces will be removed and any invalid character will be replaced with a underscore ("\_").

> If you change the default name of a test's code-behind class or if you wish to bind the test case to a different class in the code-behind file, you need to update the test's "ClassName" property in order to bind the test to the particular class. To do that, select the test case in the [project explorer](../project-explorer) so that its properties are shown in the Properties pane.

![Edit Class Name Mapping][3]

The code-behind class needs to be **public** and it should inherit **ApiTestBase** for its methods to be able to be executed by coded steps.

[Back to top](#Code-Behind-Files)

## Base Test Methods

The **ApiTestBase** base class provides two virtual methods: **OnBeforeTestStarted** and **OnAfterTestCompleted**. You can override one or both of them in your code-behind class. **OnBeforeTestStarted** will be executed before the start of any test method in your test. **OnAfterTestCompleted** will be executed after all test steps have finished (even if a test step fails). You can use them to set/clear runtime variables, to log information on the output or any other use case that you might find useful.

The example below shows hot to log messages to the test output before and after the execution of the test.

![Base Test Methods][4]

````C#
// This method will execute before the start of the test case
public override void OnBeforeTestStarted()
{
	this.Log.WriteLine("The test case is starting ...");
}

// This method will execute after all test steps in the test case have ended
public override void OnAfterTestCompleted()
{
	this.Log.WriteLine("Ending the test case ...");
}
````
````VB
' This method will execute before the start of the test Case'
Public Overrides Sub OnBeforeTestStarted()
  Log.WriteLine("The test case is starting ...")
End Sub

' This method will execute after all test steps in the test case have ended'
Public Overrides Sub OnAfterTestCompleted()
  Log.WriteLine("Ending the test case ...")
End Sub
````

[Back to top](#Code-Behind-Files)

## Context

The **ApiTestBase** base class exposes a **Context** property of type **IContext** which provides read/write access to the runtime variables of the project via the **SetValue** and **GetValue** methods.

### Context.SetValue(string name, object value, int level = 0)

The **Context.SetValue** method sets a value to a runtime variable. You can store any type of value and use it in the rest of the steps in the same test case or in other test cases in the project. Use the '*level*' property to specify what level to store the value to - the current test case only or the project root. If the method is called without a '*level*' parameter, it will store the value in the test's scope by default.

> See the [Variables](../Variables) article for more information on using variables in your project. Variables have the same behavior regardless of whether they are created in code or by a [Set Variable](../steps/set-variable) step.

#### Parameters

- *name* (type: System.String) - The name of the variable to be set
- *value* (type: System.Object) - The value to be set.
- *level* (type: System.Int32) - The level in the context inheritance chain to set the value. 0 means the current test case, 1 - the project root. Default is 0.

#### Return Value

- void

#### Examples

````C#
// This statement will create a variable named "user-name" with value "user1"
// in the scope of the current test case
this.Context.SetValue("user-name", "user1", o);

// This statement will create a variable named "user-id" with value 123
// in the root scope of the project
this.Context.SetValue("user-id", 123, 1);
````
````VB
// This statement will create a variable named "user-name" with value "user1"
// in the scope of the current test case
this.Context.SetValue("user-name", "user1", 0);

// This statement will create a variable named "user-id" with value 123
// in the root scope of the project
this.Context.SetValue("user-id", 123, 1);
````

[Back to top](#Code-Behind-Files)

### Context.GetValue(string name)

The **Context.GetValue** method returns the value of a specified runtime variable. You can use it to get the current value of any variable that you have set in the *Variables pane* of the UI, or any dinamically created runtime variable (e.g. the response body of the last executed http request step, etc.).

#### Parameters

- *name* (type: System.String) - The name of the runtime variable to retrieve.

#### Return Value

- Type: System.object
- Returns null if a value with the specified name cannot be found; otherwise the value stored in the context with all variable references resolved.

> The method will look for a variable with the specified name in the scope of the current test first. If it is not found, it will look for such a variable in the root context of the project. If a variable with that name is not found, it will return null.

> Context.GetValue has the same behavior as referencing a [variable from the UI](../variables#Referencing-Variables) using curly brackets (e.g. \{\{myVariableName\}\})

#### Examples

````C#
string userName = this.Context.GetValue("user-name").ToString();
````
````VB
Dim userName As String = Context.GetValue("user-name").ToString()
````

> Remember to cast properly your variables when using Context.GetValue. The method returns an object and you need to be aware of where and how the target value was initially created. Any variable, created manually in the Variables pane in the UI, is stored as a string.

![Casting Variables][5]

````C#
int count = 5;
this.Context.SetValue("count", count, 0);

// The "count" variable can simply be cast to int as it is initially stored in code as int
int retrievedCount = (int)this.Context.GetValue("count");
this.Log.WriteLine(retrievedCount.ToString());

// The user-id variable is created in the Variables pane and is initially created
// as a string. The value needs to be parsed in order to be stored in a in code variable
int userId = int.Parse(this.Context.GetValue("user-id").ToString());
int newUserId = userId + 1;
this.Log.WriteLine(newUserId.ToString());

// The "user-name" variable is stored as string, but you still need to convert it with .ToString()
string userName = this.Context.GetValue("user-name").ToString();
this.Log.WriteLine(userName);
````

[Back to top](#Code-Behind-Files)

## Log

The **ApiTestBase** base class exposes a **Log** property of type **ILog** which allows writing messages to the test output.

### Log.WriteLine(string message)

#### Parameters

*message (System.String)* - The custom string to write in the test output

#### Examples

````C#
this.Log.WriteLine("Logging some message from C# code ...");
````
````VB
Log.WriteLine("Logging some message from VB code ...")
````

> See the [Sample Project](../../getting-started/sample-project) for more examples.

[Back to top](#Code-Behind-Files)

## Assert

The Telerik.ApiTesting.Framework namespace provides a basic assertion framework that you can use to perform your coded verifications using the static class Assert.

The following methods ae available:

````C#
static void AreEqual<T>(T expected, T actual);

static void AreEqual<T>(T expected, T actual, string message);

static void AreNotEqual<T>(T expected, T actual);

static void AreNotEqual<T>(T expected, T actual, string message);

static void AreSame(object expected, object actual);

static void AreSame(object expected, object actual, string message);

static void IsFalse(bool condition);

static void IsFalse(bool condition, string message);

static void IsNotNull(object value);

static void IsNotNull(object value, string message);

static void IsNull(object value);

static void IsNull(object value, string message);

static void IsTrue(bool condition);

static void IsTrue(bool condition, string message);
````
````VB
Shared Sub AreEqual(Of T)(expected As T, actual As T)

Shared Sub AreEqual(Of T)(expected As T, actual As T, message As String)

Shared Sub AreNotEqual(Of T)(expected As T, actual As T)

Shared Sub AreNotEqual(Of T)(expected As T, actual As T, message As String)

Shared Sub AreSame(expected As Object, actual As Object)

Shared Sub AreSame(expected As Object, actual As Object, message As String)

Shared Sub IsFalse(condition As Boolean)

Shared Sub IsFalse(condition As Boolean, message As String)

Shared Sub IsNotNull(value As Object)

Shared Sub IsNotNull(value As Object, message As String)

Shared Sub IsNull(value As Object)

Shared Sub IsNull(value As Object, message As String)

Shared Sub IsTrue(condition As Boolean)

Shared Sub IsTrue(condition As Boolean, message As String)
````

> When an assertion fails, the execution of the test step will be terminated with status **failed** and the assertion message will be logged to the test output.

### Examples

````C#
Assert.AreEqual("administrator", actualValue);
````
````VB
Assert.AreEqual("administrator", actualValue)
````

![Assertion Error][6]

[Back to top](#Code-Behind-Files)

## See Also

* [Coded Steps](./coded-steps)
* [Standalone Code Items](./code-items)
* [Project Code Language](./project-coding-language)
* [Compile Project](./compile-project)
* [Debug Project](./debug-project)
* [Output Panel](./output-panel)
* [Add Assembly Reference](./add-assembly-reference)

[1]: /img/features/code-features/add-code-behind.png
[2]: /img/features/code-features/default-test-method.png
[3]: /img/features/code-features/edit-class-name-mapping.png
[4]: /img/features/code-features/executing-base-test-methods.png
[5]: /img/features/code-features/variables-casting.png
[6]: /img/features/code-features/assert-error.png

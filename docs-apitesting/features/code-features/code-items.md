---
title: Code Items
page_title: Code Items
description: "Progress® Test Studio® for APIs - Code Features - Code Items"
position: 3
publish: true
---

# Code Items

Code Items are standalone code files that allow you to create coded logic that is not bound to a specific test case. 

A **code item** can be useful for creating a utility class that defines a set of methods which perform common, often re-used functions. The code item can be used also as a helper class which can assist in providing some extended functionality for your test project.


## How to Create a Code Item

Right click on the **project** in the [Project Explorer](../project-explorer) or on a **folder** in the project and click on **Add Code Item**.

![Add Code Item][1]

Choose a name for the new code item and click **OK** (*RandomUsenameGenerator* in this example)

![Set Code Item Name][2]

The Code Item with name *RandomUsenameGenerator* is created under the selected location (under the *Utilities* folder in this example)

![Code Item in Project Explorer][3]


## How to Use a Code Item

This is an example on how to use a code item.

Open an already created code item (*RandomUsenameGenerator* in this example) and add a **public** method that accepts a string for *baseName*, appends a random suffix to it and returns it as a randomized username (this could be used for tests that need to create a new test user with unique username).

![Code Item Example][4]

In order to access the code item's properties and methods in a test's code-behind file, you should add a using statement in the code-behind which matches the namespace of the code item (*DemoTests.Utilities* in this example).

![Using a Code Item][5]


## See Also

* [Coded Steps](./coded-steps)
* [Code-Behind Files](./code-behind-files)
* [Project Code Language](./project-coding-language)
* [Compile Project](./compile-project)
* [Debug Project](./debug-project)
* [Output Panel](./output-panel)
* [Add Assembly Reference](./add-assembly-reference)

[1]: /img/features/code-features/add-code-item.png
[2]: /img/features/code-features/set-code-item-name.png
[3]: /img/features/code-features/code-item-in-project-explorer.png
[4]: /img/features/code-features/code-item-example.png
[5]: /img/features/code-features/using-a-code-item.png

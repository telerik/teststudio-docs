---
title: Debug Project
page_title: Compile Project
description: "Progress® Test Studio® for APIs - Code Features - Debug Project"
position: 6
published: true
---

# Debug Project

When a test project is compiled, Progress® Test Studio® for APIs generates a **.pdb** file along with the compiled **.dll** in order to allow you to debug your project.

To launch the debugger in Visual studio, you can add a `Debugger.Launch()` statement in the code that you wish to debug. (You wll need a `using System.Diagnostics` statement too.)

```C#
`Debugger.Launch();
```

```VB
`Debugger.Launch()`
```

![Add Debug Statement][1]

Once you have added your `Debugger.Launch()` statement, run your test project. You will be prompted to approve the degugger launch. Click on *"Yes, debug Telerik.ApiTesting.Runner.exe"*.

![Accept Debug Prompt][2]

Next, select a Visual Studio instance.

![Select VS Instance][3]

Finally, your code will be loaded in Visual Studio with the debugger, stooped at the `Debugger.Launch()` statement. You can keep debugging your project from that point on as an ordinary Visual Studio projet.

![Debug in Visual Studio][4]



## See Also

* [Coded Steps](./coded-steps)
* [Code-Behind Files](./code-behind-files)
* [Standalone Code Items](./code-items)
* [Project Code Language](./project-coding-language)
* [Compile Project](./compile-project)
* [Output Panel](./output-panel)
* [Add Assembly Reference](./add-assembly-reference)

[1]: /img/features/code-features/debug-launch-debugger.png
[2]: /img/features/code-features/debug-prompt.png
[3]: /img/features/code-features/debug-select-vs-instance.png
[4]: /img/features/code-features/debug-in-visual-studio.png

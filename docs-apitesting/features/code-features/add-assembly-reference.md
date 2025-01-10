---
title: Add Assembly Reference
page_title: Add Assembly Reference
description: "Progress® Test Studio® for APIs - Code Features - Add Assembly Reference"
position: 8
published: true
---

# Add Assembly Reference

If you add a coded step in Progress® Test Studio® for APIs and use logic contained in an outside assembly, you will need to add a reference to that assembly. Just like Visual Studio, project references in the Progress® Test Studio® for APIs are project specific. Adding an assembly reference in one project does not make it available to other projects.

To add an assembly reference to a project, you can either click on the **Edit Project Properties** button in the toolbar

![Edit Project Properties][1]

or right-click on the project in the Project Explorer and select **Properties**

![Project Properties Context Menu][2]

The **References** tab of the **Project Properties** dialog lists all currently added assembly references and allow adding/removing references.

![Project Properties Dialog][3]

> The first three references (*System*, *Telerik.ApiTesting.Framework* and *Telerik.ApiTesting.Framework.Abstractions*) are added by default to every project and cannot be modified.

To add a new assembly reference, click on the "Add Reference(s)" button and navigate to the directory, containing the target assembly. Select the assembly and click **Open**.

![Add reference button][4]

![Select Assembly File][5]

This will list the new assembly in the list of referenced assemblies. Click on the **Save** button to save the changes.

![New Assembly Reference Added][6]

> Note that adding an assembly reference will not copy its *.dll* file in the project. If you try to run the same project on a different machine, you need to make sure that the same assembly .dll file exists in the same path on the new machine.

> If you wish to add the *.dll* file of an assembly in your project root folder and add a reference to it from there, do not save it in the **bin** folder as it will be completely deleted every time a new build is triggered. 

## See Also

* [Coded Steps](./coded-steps)
* [Code-Behind Files](./code-behind-files)
* [Standalone Code Items](./code-items)
* [Project Code Language](./project-coding-language)
* [Compile Project](./compile-project)
* [Debug Project](./debug-project)
* [Output Panel](./output-panel)


[1]: /img/features/code-features/edit-project-properties-toolbar.png
[2]: /img/features/code-features/project-properties-context-menu.png
[3]: /img/features/code-features/project-properties-dialog.png
[4]: /img/features/code-features/add-reference-button.png
[5]: /img/features/code-features/select-assembly-file.png
[6]: /img/features/code-features/added-reference-assembly.png
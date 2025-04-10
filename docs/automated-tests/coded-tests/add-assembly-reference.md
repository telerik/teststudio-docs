---
title: Add External Library 
page_title: Add an Assembly Reference
description: "Add an external Assembly Reference in Test Studio project. How to use an external dll in Test Studio project"
position: 1
---
# Reference External Code Library File

Extending your test project with any custom code may require the usage of external libraries like various .NET assemblies, or your own specific assembly file. External assemblies are added as reference on project level in Test Studio and can be used from all tests in this project.

To add an external assembly in the project open the <a href="/features/project-settings/script-options" target="_blank">Project Settings -> Script tab</a>. The Test Studio related dlls are referenced by default and you can see these listed in this window. Click the __Add Reference__ button to browse for the external dll file.

![Add Reference][2]

Locate the assembly on your computer and click **Open**. For this example I added the _System.Windows.Forms.dll_, which can be found in the <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/gac" target="_blank">Windows GAC folder</a>. The new dll will appear in the **Project References** list.

![Added assembly][3]

> __Tip__
><br>
><br>
> We recommend to add reference to .NET assemblies from the Global Assembly Cache. This way the references should be matched out-of-the-box, if you move the project on another machine.
><br>
><br>
> If you need to add reference to a custom dll file, which is not installed in the GAC, we recommend to keep the library class file in a dedicated folder within the project root folder. That way the dll will be always deployed with the project and referenced from that location.

Once the external class library is referenced in the project you need to add `using` (or `Import`) statement in the coded file, where it will be used.

![List the dll in Code behind][5]

[2]: /img/advanced-topics/coded-steps/add-assembly-reference/fig2.png
[3]: /img/advanced-topics/coded-steps/add-assembly-reference/fig3.png
[5]: /img/advanced-topics/coded-steps/add-assembly-reference/fig5.png
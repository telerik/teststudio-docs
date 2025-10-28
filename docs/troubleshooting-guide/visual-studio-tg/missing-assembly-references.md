---
title: Missing Assembly References in Test Studio Project
page_title: Missing Assembly References in Test Studio Project
description: "Learn how to fix missing assembly reference errors in Test Studio projects after updating the Visual Studio plugin. This article explains why references break and provides step-by-step solutions for restoring project builds."
position: 1
---
# Missing Assembly References in Visual Studio (Typically After Updating Test Studio Plugin)

The problem typically occurs after updating the <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> plugin for Visual Studio.

## PROBLEM

Test Studio test projects created and maintained in Visual Studio may no longer build after upgrading the Test Studio plugin, because of missing ArtOfTest Assemblies. When you open the _References_ folder in _Solution Explorer_, some of the referenced assemblies might have a yellow warning icon signifying they cannot be resolved:

![warnings][1]

## SOLUTION

When you add your first test to a new test project in Visual Studio, references to the required assemblies are automatically referenced. By default, Visual Studio references assemblies stored in the GAC (Global Assembly Cache) with their specific version number. When you update Test Studio, all of its assemblies are replaced. The replacements carry a newer version number even though they might not contain any differences.

Because of the difference in version number, the GAC sees these replacement files as different assemblies. It assumes the assemblies needed to build the project are now missing (cannot be resolved) and your project does not build.

Make the Reference version unspecific.

1.&nbsp; Open your test project in Visual Studio.

2.&nbsp; Go to Solution Explorer.

3.&nbsp; Expand the project and open the References folder.

4.&nbsp; Select the references with a yellow warning icon. If none of them have yellow warning icons, then select them all.

5.&nbsp; Right click on the selected assemblies and choose Properties from the context menu.

![Properties][2]

Check the **Specific Version** property. Change it to False. The yellow warning icons for the selected references should disappear.  

![Specific version][3]

You must select all the unresolved references at once or repeat these steps for every unresolved reference. Once you're done, there should be no warning icons and your project should build successfully.

Also ensure you select **.NET Framework 4.7.2** as the target framework from the properties of the Test Project.

![Target Framework][4]

[1]: /img/troubleshooting-guide/visual-studio-tg/missing-assembly-references/fig1.png
[2]: /img/troubleshooting-guide/visual-studio-tg/missing-assembly-references/fig2.png
[3]: /img/troubleshooting-guide/visual-studio-tg/missing-assembly-references/fig3.png
[4]: /img/troubleshooting-guide/visual-studio-tg/missing-assembly-references/fig4.png
---
title: Add an Assembly Reference
page_title: Add an Assembly Reference
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/coded_steps/add-an-assembly-reference.aspx, /user-guide/coded_steps/add-an-assembly-reference, /advanced-topics/coded-steps/add-assembly-reference
position: 5
---
# Add an Assembly Reference (Standalone version) #

If you add a coded step in the Standalone version and use logic contained in an outside assembly, you will need to add a reference to that assembly. Just like Visual Studio, project references in the Standalone version are project specific. Adding an assembly reference in one project does not make it available to other projects.

1. Open or create a test project in the Standalone version. Click the Project tab the Show button in the Settings ribbon.

	![Settings][1]

2. The **Project Settings** menu loads.

3. Click **Script**.

4. This lists the Project References.

5. Click **Add Reference** to browse for an assembly in DLL form.

	![Add Reference][2]

6. Locate the assembly and click **Open**. The new DLL should appear in your **Project References** list. execute your test. <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> will build the coded step(s) and alert you to any compilation errors.

	![Added assembly][3]

	**Note:** You cannot use using or Imports statements directly from a coded step. You must add them to the <a href="/features/coded-steps/code-behind-file" target="_blank">code-behind file</a>.

	![Code behind][5]

* Test Studio will not find references to a DLL in the default subfolders of the project folder. These include: **bin**, **Properties**, **obj**, **Data**, **Backup**, **TestResults**, **Results**, **TestLists**, and **Profiler Configurations**. If you attempt to add a reference to a custom DLL in these locations, the following two errors patterns will appear in your application log when you run your test:

1. [09/03 10:53:15,Telerik.TestStudio.RemoteExecutor.exe(15300:14),ProjectModel] Project.Compile() : Unable to add reference Project2012SP2\Profiler Configurations\ClassLibrary5.dll.
Exception: System.IO.FileLoadException: The given assembly name or codebase was invalid. (Exception from HRESULT: 0x80131047)

2. [09/03 10:53:15,Telerik.TestStudio.RemoteExecutor.exe(15300:14),Execution] TestPlatform.OnRunnerError() : Error during remote runner execution: Compile failed: c:\Users\yee\AppData\Local\Temp\1\Projects\ce1cb993-aea7-46e9-9aa1-5d0493ddf4fc\Project2012SP2\Assembly.tstest.cs(18,7) : error CS0246: The type or namespace name 'ClassLibrary5' could not be found (are you missing a using directive or an assembly reference?)

[1]: /img/advanced-topics/coded-steps/add-assembly-reference/fig1.png
[2]: /img/advanced-topics/coded-steps/add-assembly-reference/fig2.png
[3]: /img/advanced-topics/coded-steps/add-assembly-reference/fig3.png
[4]: /img/advanced-topics/coded-steps/add-assembly-reference/fig4.png
[5]: /img/advanced-topics/coded-steps/add-assembly-reference/fig5.png
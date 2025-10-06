---
title: Test Studio Plugin Not Available in Visual Studio
page_title: Test Studio Extensions in Visual Studio Not Available 
description: "Test Studio plugin for Visual Studio is installed but I cannot create a project because the Test Studio project templates are not listed in Visual Studio. The Test Studio extensions in Visual Studio don't work. The Test Studio test is displayed as text in Visual Studio instead of showing the recorded steps."
position: 0
---
# Test Studio Project Not Available in Visual Studio

## PROBLEM

I have installed Test Studio successfully along with the Visual Studio plugin. When I try to create a project in Visual Studio there are no Test Studio project templates to use. When I'm searching the Telerik menu in Visual Studio there is no sub-menu for Test Studio.

## SOLUTION

In some occasions the extensions for Test Studio plugin, or some of them, do not get installed successfully during the overall product installation. Open the Visual Studio __Extensions->Manage Extensions__ menu to check what Test Studio extensions are listed.

The below image demos all Test Studio extensions when these are successfully added.

![Test Studio extensions in Visual Studio](/img/troubleshooting-guide/installation-problems-tg/vs-plugin-installation/vs2019-ts-extension2.png)

Depending on what extensions you see in your Visual Studio, you can proceed with manual installation of the missing components. Here are the steps to follow:

1. Open a File Explorer and navigate to the Test Studio installation folder - __C:\Program Files (x86)\Progress\Test Studio__.
1. Locate the subfolder with the version of Visual Studio you use - it contains the VSIX packages which install the Test Studio extensions for the respective Visual Studio version.
1. Run these one by one in the order the files are listed - `Common Package`, `Testing Framework`, `Test Adapter`, `Templates`, `TestStudioVSIP`.<br>

    > __Note:__ You can skip any of the packages if it is already available in the _Extensions->Manage Extensions_ list.

1. Install the VSIX packages by double clicking each of them to trigger the VSIX installer UI and follow the wizard directions.<br>
    
    > __Note:__ In case there is something to prevent the extension installation, you can see more details from the VSIX installer UI.

1. If the installation for any package fails, collect the log from the failing VSIX Installer. It can be found under the _current user's %temp%_ folder and you can recognize it by its name - it is something like `dd_VSIXInstaller_[GUID].log`. Send the log to the product team for further analysis via a support ticket.

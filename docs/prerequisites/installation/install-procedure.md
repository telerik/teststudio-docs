---
title: Test Studio Install Procedure
page_title: Installation Procedure
description: "Test Studio Installation Procedure. How to install Test Studio "
position: 2
---
# Installation Procedure

Follow the steps in this document to install Test Studio. The installation procedure is identical for the trial and the purchased version of the product.

In this article, you can find details about the following topics:

- [Prerequisites](#prerequisites)
- [Start the Installation](#start-the-installation)
- [Customize the Installation](#customize-installation)
- [Finish Installation](#finish-installation)

## Prerequisites

Before you continue, make sure that you already have <a href="/prerequisites/installation/manual-download" target="_blank">the installation file</a> available.

## Start the Installation

Once you have downloaded the Test Studio *.exe (or *.msi file), double click it to start the Installation wizard.

> __Important__
> <br>
> <br>
> Test Studio installation must be configured from a Windows Administrator account.

Click the __'Read License Agreement'__ button to get familiar with it and confirm you read it with the __'OK'__ button. If you need to read it again after the installation process is finished, you can find it available on the <a href="https://www.telerik.com/purchase/license-agreement/teststudio" target="_blank">Progress Telerik site here</a>.

By clicking the __'I Agree and Continue'__ button you confirm you agree to the terms and conditions listed in the Test Studio EULA.

![Setup Wizzard](../../img/general-information/installation/install-procedure/fig1.png)

On the next screen, click  the __'Install'__ button to perform a default installation and skip to <a href="#finish-installation">Finish Installation</a>.

![Install](../../img/general-information/installation/install-procedure/fig2.png)

If you need to check what components are selected for installation and change these, click the __'Customize'__ button.

## Customize Installation

In the __Customize__ screen you can see each separate component, which the installer wizard can add to the Test Studio installation:

- Visual Studio Plugin for the compatible Visual Studio installations on the computer, 
- Sample project folder,
- Testing Framework Samples and Templates,
- Telerik Controls Translators and
- Test Studio Services.

![Components to be installed](./img/general-information/installation/install-procedure/fig3-listOfComponents.png)

Any of these can be removed or added in the __Customize__ screen. You are also allowed to change the default installation path. After making your selections, click the __'OK'__ button to continue.

There are a few important notes to consider if you select some of the below components:

- If you have __Visual Studio__ Professional or higher installation on the machine, Test Studio plugin for Visual Studio will be automatically selected for installation.
- To use this machine as a __Storage or Scheduling Server__ in a Test Studio Scheduling setup, you must select the respective components to install the Test Studio services during initial installation or when changing the existing.
- To add the __Storage, Scheduling and Executive Dashboard features__ at a later stage, <a href="/getting-started/installation/add-services" target="_blank">you must change the existing installation</a> and select the respective components in the __Customize__ screen.
- Storage service uses <a href="https://www.mongodb.com" target="_blank">MongoDB</a> as storage database and this gets automatically installed, if not available on the machine. __MongoDB requires at least 4Gb free hard drive space__ to operate normally.

![Install services](./img/general-information/installation/install-procedure/fig3.png)

![Install services](./img/general-information/installation/install-procedure/fig4.png)

![Install services](/img/general-information/installation/install-procedure/fig5.png)

![Install VS plugin](/img/general-information/installation/install-procedure/fig6.png)

You can review all the selections and click the __'Install'__ button to start the installation process.

![Installing](/img/general-information/installation/install-procedure/fig8.png)

## Finish Installation

When the installation process is complete, the __Installation Successful__  screen is displayed and you can choose whether you want the wizard to launch the Test Studio tool and/or the Test Studio Services config wizard.

![Successfully Completed](/img/general-information/installation/install-procedure/fig9.png)

Click the __'Finish'__ button to exit the installation.

> __Note!__ When upgrading, users may encounter an error: "Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services." See <a href="/troubleshooting-guide/installation-problems-tg/error-starting-services" target="_blank">Error Starting Services troubleshooting article</a>.

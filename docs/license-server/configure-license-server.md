---
title: Test Studio Licensing Server
page_title: Test Studio Licensing Server
description: "How to setup Test Studio Licensing server? How Test Studio licensing server manages the licenses" 
position: 0
---
# Test Studio Licensing Server

Test Studio uses a per machine licensing scheme, which requires Internet connection to be activated. To ease the process of activating and distribution of licenses across multiple users Test Studio provides a __Licensing server application__, which allows floating management of the purchased licenses.

The below article describes how the Licensing server works and the process of installing and configuring it.

## How the Test Studio Licensing Server Works

The Licensing Server application requires to be __installed on a machine, which has active connection to the Internet__. This is the component, which will contact the Telerik license database to get information for the active purchased licenses, which can be used under a Telerik account.

The Licensing Server application __requires a valid Telerik account to be logged in__. This account should belong to the license holder user or to a user assigned as License Manager for the purchased licenses in the <a href="http://www.telerik.com/account/your-products/testing-tools-manage-license-keys.aspx" target="_blank">Manage Test Studio Activation Keys</a> section in your Telerik account.

The machine, on which you activate Test Studio, __requires connection to the configured Licensing Server machine only__ (may not be connected to the Internet). Start the installed Test Studio, choose the option to __activate a license through the Licensing Server__ and enter the Licensing server address. The license gets activated, if there are free slots.

Once you exit Test Studio on your local machine, the license remains reserved for the next 5 minutes. After that it is released and can be activated on another machine, which has access to the Licensing Server. Next time when you start Test Studio on a machine, which is already connected to the Licensing server, it takes a license automatically, if available.

## Install and Configure the Licensing Server Application

The Licensing server is a separate application and has its own installer file, which can be downloaded from your Telerik account.

### Installation

Once you have downloaded the Test Studio Licensing Sever *.msi file, double click it to start the Installation wizard.

> __Important__
> <br>
> <br>
> Test Studio Licensing Server installation and setup must be configured from a Windows Administrator account.

Click the __'Read License Agreement'__ button to get familiar with it and confirm you read it with the __'OK'__ button. If you need to read it again after the installation process is finished, you can find it available online on the Progress Telerik site <a href="https://www.telerik.com/purchase/license-agreement/teststudio" target="_blank">here</a>.

By clicking the __'I Agree and Continue'__ button you confirm you agree to the terms and conditions listed in the Test Studio EULA.

![Setup Wizard](/img/license-server/fig1.png)

On the next screen, click  the __'Install'__ button to trigger the installation.

![Install button](/img/license-server/fig2.png)

The installation wizard displays progress of the process.

![Installation](/img/license-server/fig3.png)

When the installation process is complete, the Telerik Test Studio Licensing Server service is automatically started. 
The __Installation Successful__  screen is displayed and you can choose whether you want the wizard to launch the Test Studio Licensing Server Configuration. Click the __Finish__ button to exit the installer wizard.

![Finish Installation](/img/license-server/fig4.png)

### Configure Licensing Server

If you haven't started the Licensing Server Configuration wizard right after the installation, you can find it in the Windows Start menu by typing _'Licensing Server'_. Ensure to start the tool from a Windows Administrator account.

![win start menu](/img/license-server/fig5.png)

In the __Telerik Account__ section enter the credentials for a Telerik account, under which are assigned the purchased licenses.

![Login Telerik account](/img/license-server/fig6.png)

In the __Licensing Server__ section you can change the __port on which the Licensing server can be accessed__ from the rest of the machines in the company. The default one is 9098 and it must be __open for inbound and outbound communication__. If you need to change it, ensure the listed one is opened in both directions and is not used from other processes.

![Licensing server port](/img/license-server/fig7.png)

The last section __Licensing Server Web Manager__ provides access to a locally hosted web page, which represents a list of the available licenses under the logged Telerik account. By default the Web Manager app can be accessed on port 8095 with the Licensing Server machine name. The port in use must be free (not used from other processes),

![Licensing server web manager](/img/license-server/fig8.png)

The Licensing Server Web Manager page allows you to view the number of activated and free licenses, and deactivate any of the activated licenses.

![web manager page](/img/license-server/fig9.png)

Activated licenses are sorted by Machine Name in ascending order. You can change the order by clicking on the title, or use the filtering options to find the machine.

![sorting and filtering](/img/license-server/fig9a.png)

Licensing Server Web Manager shows all activated licenses for the Telerik account that is used in the Licensing Server Configuration. This includes normal, manual and Licensing Server activations.

## Use the Licensing Server to Activate Test Studio License

The option to use the Licensing Server is not visible by default. To be able to see it in the License Activation wizard, a Windows Administrator account needs to add a registry key to enable the Licensing Server activation.

### Enable Licensing Server Activation Option

To enable the Licensing Server option in the Activation wizard, you need to add a registry key in the machine registry.

1. Type _'RegEdit'_ in the Windows Start menu and run the Registry Editor.
1. Navigate to __Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Telerik\TestStudio__.
1. Create a new key of type _DWORD_ and name it __EnableLicensingServerConnection__.
1. Set its value to 1.

![registry](/img/license-server/fig10.png)

The key can be added before installing the Test Studio product. If Test Studio is already installed, you can first <a href="/prerequisites/license-activation/manage-license#deactivate-license" target="_blank">deactivate the current activated license</a>, then add the registry key. Upon starting Test Studio again you will be prompted to activate a license and the option to use the Licensing server will be available.

### Activate License through the Licensing Server

Launch Test Studio and the Activation wizard appears. Next to the Telerik Account Login and Manual activation options, you can see the option __Use Licensing Server__.

![use licensing server](/img/license-server/fig11.png)

On the next screen you can enter the name of the Licensing Server machine and click the __Connect__ button to proceed. The format of address to enter is _ipaddress:port_ or _machineName:port_.

![connect to licensing server](/img/license-server/fig12.png)

Once the Activation wizard connects to the Licensing Server, it will display the available for activation licenses and you can choose which to activate. If you have purchased only one type of license, it will be activated automatically, otherwise you can choose the license type.

![choose Test Studio version](/img/license-server/fig13.png)

Test Studio starts and your machine is registered with the Licensing server. Each next time you start Test Studio it automatically contacts the server and takes a free license of the selected type.

### Disconnect from Licensing Server

In order to disconnect Test Studio from the Licensing Server and stop the automatic license distribution on this machine, you need to <a href="/prerequisites/license-activation/manage-license#deactivate-license" target="_blank">deactivate the current activated license</a>. You will see the Licensing Server that was used to activate this license.

![license deactivation](/img/license-server/fig14.png)

## Possible Errors

If you try to connect to a Licensing server in which there is no Telerik account logged in, you get a message to inform you that there is no active account. You will need to contact the administrator of the machine, which acts as a Licensing server.

![no active account](/img/license-server/fig15.png)

If you do not have access to the Licensing server, when Test Studio is started and tries to get a license key, you get the message below. You will need to contact the administartor of your machine and the machine, which acts as a Licensing server.

![no connection to licensing server](/img/license-server/fig16.png)
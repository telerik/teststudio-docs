---
title: Installation and Activation
page_title: Getting started with installing Test Studio
description: "A step by step guide on how to download, install and activate Test Studio."
previous_url: /user-guide/installation/manual_download.aspx, /user-guide/installation/manual_download, /getting-started/installation/manual_download, /user-guide/installation/install-procedure, /getting-started/installation/activate-your-license
position: 1
---
# Installation and Activation #

This article explains how to download, install and activate Telerik Test Studio. The process consists of the following steps:

- [Download Test Studio](#download-test-studio)
- [Install Test Studio](#install-test-studio)
- [Activate Your License](#activate-your-license)

## Download Test Studio ##
The easiest way to download the latest version of Test Studio is from <a href=https://www.telerik.com/teststudio target="_blank">the official website</a>.

![Download](/img/getting-started/installation-and-activation/fig00.png)

You can also download Test Studio from your telerik.com account. Once you have installed it, you can <a href="check-for-updates" target="_blank">check for updates automatically</a>, or download and install them manually:

1. Navigate to <a href="http://www.telerik.com" target="_blank">Telerik.com</a> and login to your Telerik account.

	![Log In](/img/getting-started/installation-and-activation/fig01.png)
	
	![Log In](/img/getting-started/installation-and-activation/fig02.png)

2. To download the latest version of Test Studio, including Service Packs and Latest Internal Builds, open the Manage products menu and select Test Studio. 

	![Test Studio product](/img/getting-started/installation-and-activation/fig03.png)

3. From the Test Studio product page, click the __Download__ link.

	![Download](/img/getting-started/installation-and-activation/fig04.png)

4. Select the official release or latest internal build. Download the installer and execute the file to install that version or upgrade an existing Test Studio installation the newer version.

	![Install](/img/getting-started/installation-and-activation/fig05.png)

## Install Test Studio ##

1. After you have [downloaded the install file](#download-test-studio), locate it using Windows Explorer and double click it to launch the installer.
2. Click __Read License Agreement__, then __OK__, then I __Agree - Continue__.

	![Setup Wizzard](/img/getting-started/installation-and-activation/fig06.png)

3. To take the defaults, click __Install__ and skip to step 6. Otherwise click the __Customize__ button. <br><br>**Note**: This button is not available when you download the *.exe installer directly from our site. In order to access it you should download the *.msi installer from your Telerik.com account.

	![Install](/img/getting-started/installation-and-activation/fig07.png)

4. On this screen you can select which features to install by clicking __Customize__ button. You can also change the installation path. After making your selections, click __OK__ to continue.

	* To use this machine as a Storage Server or Scheduling Server, you must install the appropriate services at this time.
	* To add the Storage and Scheduling Services features, <a href="/getting-started/installation/add-services" target="_blank">you must complete the installation and perform a change using the installer</a>.
	* Storage server uses <a href="https://www.mongodb.com" target="_blank">MongoDb</a> as storage database. MongoDb requires at least 4Gb hard drive space to operate normally.
	* If you have installed Visual Studio on the machine Test Studio plugin for Visual Studio will be also installed.

	![Install services](/img/getting-started/installation-and-activation/fig08.png)

	![Install services](/img/getting-started/installation-and-activation/fig09.png)

	![Install VS plugin](/img/getting-started/installation-and-activation/fig10.png)

5. Review all the selections and click __Install__ to start the installation process.

	![Installing](/img/getting-started/installation-and-activation/fig11.png)

6. When the install is complete, the __Installation Successful__  screen is displayed.

	![Successfully Completed](/img/getting-started/installation-and-activation/fig12.png)

7. Click __Finish__ to exit the installation.

	* Note: When upgrading, users may encounter an error: "Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services." See <a href="/troubleshooting-guide/installation-problems-tg/error-starting-services" target="_blank">Error Starting Services troubleshooting article</a>.

## Activate Your License ##

After installing Telerik <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a>, you will be asked to activate your license. During this process, your machine creates its own unique key and provides it to our server. We use this key to generate a unique license key for the installation of the product. This article discusses how to go through this process and provides a guided walk-through. All users, both trial and purchased, will need to activate their product after installation before they can begin using the tool.
 
The below process assumes that you have not launched the Standalone or VS plugin version after the installation completed. If you have already launched Test Studio and are ready to input your licensing data (user email and password), skip to step 3.

1. Launch Test Studio:
	* __Standalone version__: Click Start > Programs > Telerik > Test Studio > Launch Test Studio
	* __Visual Studio plugin__: Click Start > Programs > Microsoft Visual Studio 20XX > Microsoft Visual Studio 20XX
	

2. This step is for VS plugin users only. Standalone users can skip to step 3. If you have a project with a Test Studio test in it, open the project within Visual Studio, and then the test. If you do not have a solution or project of this type, perform steps 1-3 listed here to begin activation.
	
3. Input the email address and password that correspond to your <a href="https://www.telerik.com/login/v2/telerik?returnurl=%2f" target="_blank">Telerik.com</a> account.

	![Log In screen](/img/getting-started/installation-and-activation/fig13.png)

4.	Click __Login.__

5.	Chose your purchased version and click __Activate Selected Version__ (please note that you can change your version later on).

	![Choose version](/img/getting-started/installation-and-activation/fig14.png)

6.	If you are activating purchased version and you have more than one purchases you will have to choose which license to activate. __NOTE: The following screen does NOT appear if you are activating trial version or have only one purchase.__

	![Choose license](/img/getting-started/installation-and-activation/fig15.png)

7.	Click __Activate Selected License.__ If the activation is successful the you can start using Test Studio.

    ![Activation successful](/img/getting-started/installation-and-activation/fig16.png)

8.	If your machine was freshly imaged or replaced and you need to re-activate your license (__0 seats available__) on the new machine, please visit <a href="/getting-started/installation/re-activating-your-license" target="_blank">Re-Activating your License</a> article.

9.	If you perform the above process and you receive the screen below, click on Activate Manually and follow this article for <a href="manual-activation" target="_blank">Manual Activation</a>.

	![Couldn't log](/img/getting-started/installation-and-activation/fig17.png)


<div><a style="float:right" href="/getting-started/first-project">Go to Your First Project</a></div>
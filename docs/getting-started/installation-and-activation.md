---
title: Installation and Activation
page_title: Getting started with installing Test Studio
description: "A step by step guide on how to download, install and activate Test Studio."
position: 1
publish: false
---
# Installation and Activation 

This article explains how to download, install and activate Telerik Test Studio. The process consists of the following steps:

1. [Download Test Studio](#download-test-studio)
2. [Install Test Studio](#install-test-studio)
3. [Activate Your License](#activate-your-license)

## Download Test Studio 
The easiest way to download the latest version of Test Studio is from <a href=https://www.telerik.com/teststudio target="_blank">the official website</a>.

![Download](/img/getting-started/installation-and-activation/fig00.png)

You can also download Test Studio from your telerik.com account.

1. Navigate to <a href="http://www.telerik.com" target="_blank">Telerik.com</a> and login to your Telerik account.

	![Log In](/img/getting-started/installation-and-activation/fig01.png)
	
	![Log In](/img/getting-started/installation-and-activation/fig02.png)

2. To download the latest version of Test Studio, including Service Packs and Latest Internal Builds, open the Manage products menu and select Test Studio.

	![Test Studio product](/img/getting-started/installation-and-activation/fig03.png)

3. From the Test Studio product page, click the __Download__ link.

	![Download](/img/getting-started/installation-and-activation/fig04.png)

4. Select the official release or latest internal build. Download the installer and execute the file to install that version or upgrade an existing Test Studio installation to the newer version.

	![Install](/img/getting-started/installation-and-activation/fig05.png)

## Install Test Studio 

1. After you have [downloaded the install file](#download-test-studio), locate it using Windows Explorer and double click it to launch the installer.
2. Click the __Read License Agreement__ to read the  <a href="http://www.telerik.com/purchase/license-agreement/teststudio" target="_blank">Test Studio EULA</a>. When ready click __OK__ and then __I Agree – Continue__ button to confirm you agree with the terms of the license.

	![Setup Wizzard](/img/getting-started/installation-and-activation/fig06.png)

3. To take the defaults, click __Install__ and skip to step 6. Otherwise click the __Customize__ button. <br><br>**Note**: This button is not available when you download the *.exe installer directly from our site. In order to access it you should download the *.msi installer from your Telerik.com account.

	![Install](/img/getting-started/installation-and-activation/fig07.png)

4. Once you select the __Customize__ button, you can choose whether to install some optional components or to change the installation path. After making your selections, click __OK__ to continue

	* To use this machine as a Storage Server and/or Scheduling Server, you need to install the appropriate services at this time or [add these at a later moment](/general-information/installation/add-services).
	* To add the Storage and Scheduling Services features, <a href="/general-information/installation/add-services" target="_blank">you must complete the installation and perform a change using the installer</a>.
	* Storage server uses <a href="https://www.mongodb.com" target="_blank">MongoDb</a> as storage database and its minimum requirement is 4GB hard drive space to operate normally.
	* If you have Visual Studio on the machine, Test Studio plugin for Visual Studio will be also installed for all detected Visual Studio installations.

	![Install services](/img/getting-started/installation-and-activation/fig08.png)

	![Install services](/img/getting-started/installation-and-activation/fig09.png)

	![Install VS plugin](/img/getting-started/installation-and-activation/fig10.png)

5. Review the custom selections and click __OK__ and then __Install__ to start the installation process.

	![Installing](/img/getting-started/installation-and-activation/fig11.gif)

6. When the install is complete, the __Installation Successful__  screen is displayed.

	![Successfully Completed](/img/getting-started/installation-and-activation/fig12.png)

7. Click __Finish__ to exit the installation.

	* Note: When upgrading, users may encounter an error: "Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services." See <a href="/troubleshooting-guide/installation-problems-tg/error-starting-services" target="_blank">Error Starting Services troubleshooting article</a>.

Once you have installed Test Studio, you can <a href="/general-information/installation/check-for-updates" target="_blank">check for updates automatically</a>, or download and install them manually.

## Activate Your License 

After installing Telerik <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a>, you will be asked to activate your license. During this process, your machine creates its own unique key and provides it to our server. We use this key to generate a unique license key for the installation of the product. This tutorial below describes how to go through this process and provides a guided walk-through. All users, both trial and purchased, will need to activate their product after installation before they can begin using the tool.
 
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

8.	If your machine was freshly imaged or replaced and you need to re-activate your license (__0 seats available__) on the new machine, please visit <a href="/general-information/installation/re-activating-your-license" target="_blank">Re-Activating your License</a> article.

9.	If you perform the above process and you receive the screen below, click on Activate Manually and follow this article for <a href="/general-information/installation/manual-activation" target="_blank">Manual Activation</a>.

	![Couldn't log](/img/getting-started/installation-and-activation/fig17.png)


<div><a style="float:right" href="/getting-started/first-project">Go to <strong>Your First Project</strong></a></div>


## Test Execution 

It is time to execute the recorded test or <a href="/general-information/test-execution/test-lists-standalone" target="_blank">test list</a> and observer the execution process. At the end of the execution, you will see which step passed and which failed, along with <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log" target="_blank">the execution log</a>.

> __Note!__ While a test is being executed, **do not start another instance of the same browser or any other application** until the run is finished!

1. Once a test scenario is already recorded, click the **Execute** button in the Test ribbon.

    ![Test Studio](/img/getting-started/first-project/fig08.png)

2. Select Internet Explorer as the execution browser and click **Run**. This step will be skipped if you have already set a preferred browser from the <a href="/general-information/test-execution/quick-execution" target="_blank">Web ribbon</a>.

    ![Select browser](/img/getting-started/first-project/fig09.png)

3. The Test Studio Test Runner first launches a command prompt window and opens the selected browser.

    ![Test Runner](/img/getting-started/first-project/fig10.png)

4. By default in the lower right of your screen there is a ribbon which indicates the current step, includes play and pause ability, and shows additional Debug Options if you set a <a href="/features/test-maintenance/steps-pane" target="_blank">Breakpoint to any step</a>. This is the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-visual-debugger" target="_blank">visual debugger</a> and is a feature you could turn on or off.

    ![Visual Debugger Indicator](/img/getting-started/first-project/fig11.png)

    Click **Debugging Options** icon in the Test ribbon or the Visual Studio toolbar to turn the debugger on/off and customize the Auto-Pause Options, if errors occur during the execution.

    ![Test Studio](/img/getting-started/first-project/fig12.png)

5. Enable the **Toggle Annotation** button to have the browser annotate each step with a brief message and by highlighting that step's element. This will also slow the test run by the configured amount (in milliseconds) between each step. You can set it either from the menu or by entering a custom value.

    ![Toggle Annotation](/img/getting-started/first-project/fig13.png)

## Execution Results 

When the test execution is complete, there will be an indication for each step if it *Passed* or *Failed*. Test results are automatically generated and details can be reviewed by clicking on **View Log**. 

![View log](/img/getting-started/first-project/fig14.png)

The results from test list executions are available in the **Results** tab.
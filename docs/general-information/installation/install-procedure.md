---
title: Install Procedure
page_title: Installation Procedure
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Installation Procedure #

1. After you have downloaded the install file, locate it using Windows Explorer and double click it to launch the installer.
2. Click __Read License Agreement__, then __OK__, then I __Agree - Continue__.

	![Setup Wizzard](/img/general-information/installation/install-procedure/fig1.png)

3. To take the defaults, click __Install__ and skip to step 6. Otherwise click the __Customize__ button. <br><br>**Note**: This button is not available when you download the *.exe installer directly from our site. In order to access it you should download the *.msi installer from your Telerik.com account.

	![Install](/img/general-information/installation/install-procedure/fig2.png)

4. On this screen you can select which features to install by clicking __Customize__ button. You can also change the installation path. After making your selections, click __OK__ to continue.

	* To use this machine as a Storage Server or Scheduling Server, you must install the appropriate services at this time.
	* To add the Storage and Scheduling Services features, <a href="/getting-started/installation/add-services" target="_blank">you must complete the installation and perform a change using the installer</a>.
	* Storage server uses <a href="https://www.mongodb.com" target="_blank">MongoDb</a> as storage database. MongoDb requires at least 4Gb hard drive space to operate normally.
	* If you have installed Visual Studio on the machine Test Studio plugin for Visual Studio will be also installed.

	![Install services](/img/general-information/installation/install-procedure/fig3.png)

	![Install services](/img/general-information/installation/install-procedure/fig4.png)

	![Install VS plugin](/img/general-information/installation/install-procedure/fig5.png)

5. Review all the selections and click __Install__ to start the installation process.

	![Installing](/img/general-information/installation/install-procedure/fig7.png)

6. When the install is complete, the __Installation Successful__  screen is displayed.

	![Successfully Completed](/img/general-information/installation/install-procedure/fig8.png)

7. Click __Finish__ to exit the installation.

	* Note: When upgrading, users may encounter an error: "Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services." See <a href="/troubleshooting-guide/installation-problems-tg/error-starting-services" target="_blank">Error Starting Services troubleshooting article</a>.



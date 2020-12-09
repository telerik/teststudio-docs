---
title: Integration
page_title: Quality Center Integration
description: "Maintain the Quality center connected project from Test Studio"
previous_url: /user-guide/extensions/quality-center/integration.aspx, /user-guide/extensions/quality-center/integration
position: 0
---
# Quality Center Integration

Push your tests and test results to Quality Center, leveraging your existing QC process for tests built in Test Studio.

> __Important!__
><br>
><br>
> As of Test Studio release __R3 2020 SP1 (v.2020.3.1209)__ Quality Center integration is no longer visible in the main Test Studio user interface. If you want to continue using it, see <a href="#enable-quality-center-in-test-studio-2020-r3-sp-release">here</a> how to enable it.

## Connect the Quality Center Solution with Test Studio project

> Quality Center version 11.0 and above is supported.

1. On the **Project** tab, click the **Quality Center** button in the **Extensions** ribbon.

	![Quality Center Button][1]

2. Enter the Quality Center URL and click **Connect**.

	![Connect][2]

3. Enter your Username and Password and click **Login**.

	![Login][3]

4. Select which project to connect with Test Studio and click Open project.
5. The **Sync Project with Quality Center** screen loads.

	![Sync][4]

6. Select **Tests** or **Results** in the upper-left. Select one or multiple (using Ctrl + Click or Shift + Click) tests or results to push to QC. Then click **Publish > All** or **Selected**.

	![Selected][5]

7. If you make changes to a test that has already been pushed, click the **Sync** button to update the test in QC.

	![Sync button][6]

8. The pushed test/result now resides in Quality Center.

	![QC view][6]

## Enable Quality Center in Test Studio 2020 R3 SP Release

The button to connect a Test Studio project to a __Quality Center__ solution is __removed in Test Studio release R3 SP 2020 (v.2020.3.1209)__. You still can bring up the button back in the product.

Open a File Explorer and navigate to the Test Studio installation _Bin_ sub-folder (the default location is _C:\Program Files (x86)\Progress\Test Studio\Bin_). Locate the _Telerik.TestStudio.exe.config_ file and modify it as follows:

1. Open the file with a text editor (like Notepad++).
1. In the _appSettings_ section add a key _ShowQCPlugin_ and set its value to true. See example below.

	```
	<appSettings>
		<add key="CommandLineRun" value="True" />
		<add key="PersistOnEachStep" value="False" />
		<add key="ShowQCPlugin" value="False" />
	</appSettings>
	```

1. Restart Test Studio and the QC button will be back in the _Project Ribbon_.

[1]: /img/features/integration/quality-center/integration/fig1.png
[2]: /img/features/integration/quality-center/integration/fig2.png
[3]: /img/features/integration/quality-center/integration/fig3.png
[4]: /img/features/integration/quality-center/integration/fig4.png
[5]: /img/features/integration/quality-center/integration/fig5.png
[6]: /img/features/integration/quality-center/integration/fig6.png
[7]: /img/features/integration/quality-center/integration/fig7.png
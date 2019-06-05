---
title: Add Path to Environment Variables
page_title: Add Path to Environment Variables
description: "Test Studio Add Path to Environment Variables. Workaround to avoid always navigate to the Bin directory each time you want to call the execution engine"
previous_url: /user-guide/test-runners/addpathtoenvironmentvariables.aspx, /user-guide/test-runners/addpathtoenvironmentvariables
position: 1
---
# Add Path to Environment Variables

It can get tedious to always have to navigate to the Bin directory each time you want to call the execution engine. A great workaround is to register this path with Windows so that you can call ArtOfTest.Runner.exe from any directory within the command prompt.

## Windows 10

1.&nbsp; From the Desktop, right-click the Start button and click **System**.

![System][7]

2.&nbsp; After the **System** screen appears, select **Advanced system settings**.

![Advanced System Settings][8]

3.&nbsp; This will open the **System Properties** window. Select the **Advanced** tab and then the **Environment Variables** button.

![Environment Variables][9]

4.&nbsp; Under the **System variables** section, scroll down and highlight the **Path** variable. Click the **Edit** button.

![Path Button][10]

5.&nbsp; In the Edit screen, click **New** and add the path to the **Bin** directory of Test Studio. In this example, I added **C:\Program Files (x86)\Telerik\Test Studio\Bin**.

![Edit System Variable][11]

> Please note that as of version 2017 R3 the default installation path for new installation is C:\Program Files (x86)\Progress\Test Studio.

6.&nbsp; Click the **OK** button. You now have access to the execution engine from any directory on your computer. Make sure you start a new instance of the command prompt to get the updated variables.

![CMD][12]

## Windows 7

1.&nbsp; To do this, right mouse click on **Computer** and select **Properties**.

![Properties][1]

2.&nbsp; After the **System** screen appears, select **Advanced system settings**.

![Advanced System Settings][2]

3.&nbsp; This will open the **System Properties** window. Select the **Advanced** tab and then the **Environment Variables** button.

![Environment Variables][3]

4.&nbsp; Under the **System variables** section, scroll down and highlight the **Path** variable. Click the **Edit** button.

![Path Button][4]

5.&nbsp; In the Edit screen, append the path to the **Bin** directory to the end of the string that already exists in the **Variable value** text box (with a semicolon before the path). In this example, I added "**;C:\Program Files (x86)\Telerik\Test Studio\Bin** - Notice that I added a semicolon to separate the previous path from the path to the *ArtOfTest.Runner.exe* directory.

![Edit System Variable][5]

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

6.&nbsp; Click the **OK** button. You now have access to the execution engine from any directory on your computer. Make sure you start a new instance of the command prompt to get the updated variables.

![CMD][6]

[1]: /img/features/test-runners/add-path-environment-variables/fig1.png
[2]: /img/features/test-runners/add-path-environment-variables/fig2.png
[3]: /img/features/test-runners/add-path-environment-variables/fig3.png
[4]: /img/features/test-runners/add-path-environment-variables/fig4.png
[5]: /img/features/test-runners/add-path-environment-variables/fig5.png
[6]: /img/features/test-runners/add-path-environment-variables/fig6.png
[7]: /img/features/test-runners/add-path-environment-variables/fig7.png
[8]: /img/features/test-runners/add-path-environment-variables/fig8.png
[9]: /img/features/test-runners/add-path-environment-variables/fig9.png
[10]: /img/features/test-runners/add-path-environment-variables/fig10.png
[11]: /img/features/test-runners/add-path-environment-variables/fig11.png
[12]: /img/features/test-runners/add-path-environment-variables/fig12.png

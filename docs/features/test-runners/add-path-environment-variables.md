---
title: Add Test Studio Installation Path to Environment Variables
page_title: Add Test Studio Installation Path to Environment Variables
description: "Test Studio CLI Runner, Test Studio Command Line Runner, Add the Test Studio installation folder as PATH in Environment Variables. Avoid always changing the working directory to the Test Studio Installation Bin folder by each call of the Test Studio execution engine ArtOftest.Runner.exe."
previous_url: /user-guide/test-runners/addpathtoenvironmentvariables.aspx, /user-guide/test-runners/addpathtoenvironmentvariables
position: 5
---
# Add Test Studio Installation Path to Environment Variables

Once you have developed an automated test solution with <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a>, you can execute the test and test lists through the command prompt using the Test Studio command line runner called <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner.exe</a>.

Whenever you want to call the execution engine, you need to navigate to the Test Studio installation _Bin_ sub-folder. This can get tedious, for example, when integrating the automated test solution into continuous integration workflow. For such occasions you can rely on the Windows operating system features, which allows you to call an executable directly from the command line. Namely, this is the system variable __PATH__ that Windows operating system uses to locate needed executables from the command line or Terminal window.

If you add the __Test Studio installation _Bin_ sub-folder__ to the __PATH__ environment variable, you will be able to call the Test Studio command line runner __ArtOfTest.Runner.exe__ from any directory within the command prompt.

Below you can find the necessary steps to add the _Bin_ sub-folder to the __PATH__ environment variable in Windows 10 and Windows 7.

## Windows 10

1.&nbsp; Open __Windows Control Panel__ and navigate to __System__ (Control Panel->System and Security->System).

2.&nbsp; After the **System** screen appears, select **Advanced system settings**.

![Advanced System Settings][8]

3.&nbsp; This will open the **System Properties** window. Select the **Advanced** tab and then the **Environment Variables** button.

![Environment Variables][9]

4.&nbsp; Under the **System variables** section, scroll down and highlight the **Path** variable. Click the **Edit** button.

![Path Button][10]

5.&nbsp; In the Edit screen, click **New** and add the path to the **Bin** directory of Test Studio. In this example, I added **C:\Program Files (x86)\Progress\Test Studio\Bin**.

![Edit System Variable][11]

6.&nbsp; Click the **OK** button. You now have access to the __ArtOfTest.Runner.exe__ from any directory on your computer. Make sure you start a new instance of the command prompt to get the updated variables.

![CMD][12]

## Windows 7

1.&nbsp; To do this right-click on **Computer** and select **Properties**.

![Properties][1]

2.&nbsp; After the **System** screen appears, select **Advanced system settings**.

![Advanced System Settings][2]

3.&nbsp; This will open the **System Properties** window. Select the **Advanced** tab and then the **Environment Variables** button.

![Environment Variables][3]

4.&nbsp; Under the **System variables** section, scroll down and highlight the **Path** variable. Click the **Edit** button.

![Path Button][4]

5.&nbsp; In the Edit screen, append the path to the **Bin** directory to the end of the string that already exists in the **Variable value** text box (with a semicolon before the path). In this example, I added "**;C:\Program Files (x86)\Progress\Test Studio\Bin** - Notice that I added a semicolon to separate the previous path from the path to the *ArtOfTest.Runner.exe* directory.

![Edit System Variable][5]

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

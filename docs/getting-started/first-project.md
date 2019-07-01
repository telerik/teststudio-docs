---
title: Your First Project
page_title: Create your first Test Studio project
description: "A step by step guide on how to record and execute your first Test Studio project."
position: 2
---
# Your First Project #

Once you have successfully installed and activated Test Studio, you are ready to setup the machine for testing and create your first automation test. The process is divided in several steps:

1. [Create new project](#create-new-project)
2. [Calibrate your browser for testing](#calibrate-your-browser)
3. [Add a Test to the Project](#add-a-test-to-the-project)
4. [Test Recording](#test-recording)
5. [Test Execution](#test-execution)
6. [Execution Results](#execution-results)

## Create New Project ##

When you launch Test Studio, you will see the [**Welcome Screen**](/general-information/start-a-project/welcome-screen). It lets you open or create projects, and see notifications about software updates and news related to the product.

In the [**Create project**](/general-information/start-a-project/welcome-screen#create-a-new-project) section you could choose among different type projects - **Web & Desktop**, **Mobile** or **API**. Let's create a **Web & Desktop** project for the current demonstration, specify its name and location and click the **Create** button.

![Create Project](/img/getting-started/first-project/fig00.png)

>After the project is successfully created, you can open the <a href="/general-information/start-a-project/in-product-tips-tricks" target="_blank">Tips and Tricks</a> from the top right corner of Test Studio. The popup dialog has many useful references to the documentation and a short video on some of the topics.

You can explore a sample **Web & Desktop** or **API** project, from the [**Get Started**](/general-information/start-a-project/welcome-screen#get-started) section. And you can learn more about the **Mobile** module in Test Studio.

![Get Started Projects](/img/getting-started/first-project/fig01.png)

## Configure Your Browser for Testing ##

Once the test project is created you need to configure your browser for testing, we call this "browser calibration". This is done to ensure flawless and consistent automation process. We have implemented a feature to [automatically calibrate the browser](/features/project-settings/browsers) out of the box without manual actions. In this case we will be using Internet Explorer.

>**Note:** Other supported browsers like [Chrome](/general-information/configure-your-browser/chrome) and [Firefox](/general-information/configure-your-browser/firefox) require the Progress Test Studio extension, where [Microsoft Edge](/general-information/configure-your-browser/edge) uses the WebDriver.

## Add a Test to the Project ##

The same project can have different types of tests, organized in folders. Those test can be later added to <a href="/general-information/test-execution/test-lists-standalone" target="_blank">test lists</a>. For your first test in this project add a new **Web** test.

1. Go to the *Project* ribbon and click on the **Add New Test** button.

    ![Add new test Project Ribbon](/img/getting-started/first-project/fig02.png)

2. In the *Create new test* dialog select **Web** and enter a meaningful name for it.

    ![Add new test](/img/getting-started/first-project/fig03.png)

You can find more information on all test types available in a Test Studio Web & Desktop project:

*	<a href="/general-information/test-recording/overview" target="_blank">**Web Test**</a>
*	<a href="/features/testing-types/load-testing/Overview" target="_blank">**Load Test**</a>
*	<a href="/features/testing-types/wpf-testing/wpf-test" target="_blank">**WPF Test**</a>
*	<a href="/features/testing-types/manual-testing/overview" target="_blank">**Manual Test**</a>

## Test Recording ##

The Test Studio Recorder will add all actions against the application to your test. You can enable the highlight mode from the recording toolbar and explore the <a href="/features/recorder/dom-explorer" target="_blank">DOM tree</a> of the page and add the necessary <a href="/features/recorder/verifications/overview" target="_blank">verifications steps</a>.

1. Double click the newly created test to open it. Click the ***Record*** button in the *Tests* ribbon or press **CTRL+R**.

    ![Add new test Project Ribbon](/img/getting-started/first-project/fig04.png)

2. In the *Recording* dialog type the URL you want to navigate to, select Internet Explorer browser and press Enter or the *Record* button. You can choose a URL from your recent URLs.

    > **Note**: Selecting the recording browser will be skipped if you have already set a preferred browser from the <a href="/general-information/test-execution/quick-execution" target="_blank">Test ribbon</a>.

    ![Choose browser](/img/getting-started/first-project/fig05.png)

3. Once the selected browser navigates to the desired page, the recorder gets attached to it. A navigate step is recorded in the *Steps* pane and you can continue recording the next actions as per the required scenario.

    ![Attached recorder](/img/getting-started/first-project/fig06.png)

4. Lets navigate to the [Test Studio documentation](https://docs.telerik.com/teststudio/). Click on **DOCS & SUPPORT** button, find **Test Studio** and click it and click on **Documentation**. All of those actions are recorded as steps in the test.

    ![Step pane](/img/getting-started/first-project/fig07.png)

## Test Execution ##

It is time to execute the recorded test or <a href="/general-information/test-execution/test-lists-standalone" target="_blank">test list</a> and observer the execution process. At the end of the execution, you will see which step passed and which failed, along with <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log" target="_blank">the execution log</a>.

> While a test is being executed **do not start another instance of the same browser** until the run is finished!

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

## Execution Results ##

When the test execution is complete, there will be an indication for each step if it *Passed* or *Failed*. Test results are automatically generated and details can be reviewed by clicking on **View Log**. 

![View log](/img/getting-started/first-project/fig14.png)

The results from test list executions are available in the **Results** tab.

<div><a href="/getting-started/installation-and-activation">Go to <strong>Installation and Activation</strong></a><a style="float:right" href="/getting-started/analyze-the-results">Go to <strong>Analyze the Results</strong></a></div>
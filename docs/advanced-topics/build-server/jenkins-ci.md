---
title: Jenkins CI
page_title: Jenkins CI
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/command-line-test-execution/continuous-integration/jenkins_ci.aspx, /user-guide/command-line-test-execution/continuous-integration/jenkins_ci
position: 2
---
#Jenkins CI#

Build and execute Test Studio tests in Jenkins CI by following these steps:

1.&nbsp; **Install the Java Web Archive (.war) for Jenkins CI**. Test Studio tests should not be run from a Windows Service account. Because the Windows native package for Jenkins CI runs as a Windows Service, Test Studio requires the Java Web Archive version to run properly.

![Download Jenkins][1]

2.&nbsp; **Run the Jenkins Listener on a custom port**. By default, the Jenkins Listener runs on port 8009 -- the same port as the Test Studio Scheduling Service. When installing the .war, use a command line argument to configure a different, non-conflicting port number for the listener (that is, avoid port numbers 8009, 8010, 8011, 8012, and 8013). For example:

*java -jar jenkins.war --ajp13Port=8019*

> As of release **R1 2018 (v2018.1.301)** you could install and use the <a href="/advanced-topics/build-server/jenkins-ci-plugin" target="_blank">Jenkins Test Studio Plugin</a>.

3.&nbsp; **Create a free-style software project**. Create a job and select 'Build a free-style software project'.

![Free-style software project][2]

4.&nbsp; **Add a Windows batch command build step**. Under the 'Add build step menu,' select 'Execute Windows batch command'.

![Command build step][3]

5.&nbsp; **Input ArtOfTest.Runner command line command to execute tests**. Under 'Execute Windows batch command', input the ArtOfTest.Runner command to execute your test or test list, including <a href="/features/test-runners/artoftest-runner" target="_blank">full path to ArtOfTest.Runner.exe and appropriate arguments</a>.

![Arguments][4]

Your test execution step is now ready to save and run.

##Build a Visual Studio project or a Solution

1. **Configure MSBuild Plugin to build coded tests**.

	1.1 Under the **Jenkins** menu, open **Manage Jenkins > Manage Plugins**.

	![Manage plugins][5]

	1.2 Select and install the **MSBuild Plugin**.

	![MSBuild Plugin][6]

	1.3 Configure MSBuild Plugin according to <a href="https://wiki.jenkins-ci.org/display/JENKINS/MSBuild+Plugin" target="_blank">Jenkins CI instructions</a>.

2. **Add MSBuild Step**. Under **Build**, open the **Add build step** and select **Build a Visual Studio project or solution using MSBuild**.

	![MSBuild Step][7]

3. **Specify a Visual Studio project or solution for your test**. Save the build configuration.

	![Specify a Visual Studio project][8]

##Attach the results files to the Job##

1.	Add "**out**" parameter in the batch command. It should point to the default jenkins workspace **(C:\Users\[userName]\.jenkins\jobs\test\workspace\%JOB_NAME%%BUILD_NUMBER%**) so the results files are outputted in a folder with an unique name (Job Name + Build Number).

	
	![Out parameter][9]

2. Add a post-build action of type "**Archive the artifacts**".

	![Archive the artifacts][10]

3. Type *${JOB_NAME}${BUILD_NUMBER}\\*** in the "**Files to archive**" field so all the results files can be taken.

	![Files to archive][11]

4. After the build completion all the results files will be attached to it.

	![Files to archive][12]

5. Click **Build Artifacts** and download the files in a *.zip file (it will keep the folder structure) and open the **.aiiresult* file.

	![Save in zip file][13]

Your Jenkins CI build is now ready to run.

**Disclaimer**:

In case you are running Test Studio tests using <a href="http://www.donaldsimpson.co.uk/2011/10/06/jenkins-slave-nodes/" target="_blank">Jenkins slaves</a> you may experience the following exception:

<div>
The process is not running in 'Interactive Mode'! The 'DialogMonitor' has been disabled for this Browser.<br>

<i>TestExecuteProxy.ExecuteTest() : EXCEPTION! (see below)<br>
Outer Exception Type: System.TimeoutException<br>
Message: Wait for condition has timed out<br>
HRESULT: 0x80131505 (Official ID (if app.) = COR_E_TIMEOUT, Error Bit = FAILED, Facility = FACILITY_URT, Code = 5381)<br>
Call Stack:<br>
at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo, Object target)<br>
at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)<br>
at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)<br>
at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)<br>
at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect, <br>ProcessWindowStyle windowStyle, String arguments)<br>
at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InitializeWeb(ExecutionEngineCreateParams initParams)<br>
at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.CreateAndInitializeEngine(Test test, ExecutionEngineCreateParams cp)<br>
at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)<br></i>

</div>

The problem is that Jenkins slaves cannot be ran as service. This will cause the automation to fail with the above exception. In this case you should start Jenkins service headless.

Example:

**java -jar slave.jar -jnlpurl http://$HOST:$PORT/computer/$SLAVEMACHINE/slave-agent.jnlp**

or

**javaws http://$HOST:$PORT/computer/$SLAVEMACHE/slave-agent.jnlp**

[1]: /img/advanced-topics/build-server/jenkins-ci/fig1.png
[2]: /img/advanced-topics/build-server/jenkins-ci/fig2.png
[3]: /img/advanced-topics/build-server/jenkins-ci/fig3.png
[4]: /img/advanced-topics/build-server/jenkins-ci/fig4.png
[5]: /img/advanced-topics/build-server/jenkins-ci/fig5.png
[6]: /img/advanced-topics/build-server/jenkins-ci/fig6.png
[7]: /img/advanced-topics/build-server/jenkins-ci/fig7.png
[8]: /img/advanced-topics/build-server/jenkins-ci/fig8.png
[9]: /img/advanced-topics/build-server/jenkins-ci/fig9.png
[10]: /img/advanced-topics/build-server/jenkins-ci/fig10.png
[11]: /img/advanced-topics/build-server/jenkins-ci/fig11.png
[12]: /img/advanced-topics/build-server/jenkins-ci/fig12.png
[13]: /img/advanced-topics/build-server/jenkins-ci/fig13.png

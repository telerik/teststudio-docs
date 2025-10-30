---
title: Jenkins CI
page_title: Jenkins CI
description: "Integrate Test Studio tests in Jenkins continuous integration. Execute Test Studio tests with Jenkins."
previous_url: /user-guide/command-line-test-execution/continuous-integration/jenkins_ci.aspx, /user-guide/command-line-test-execution/continuous-integration/jenkins_ci
position: 4
---
# Jenkins CI

Build and execute <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests in Jenkins CI by following these steps:

## Install the Java Web Archive (.war) for Jenkins CI

Test Studio tests should not be run from a Windows Service account. Because the Windows native package for Jenkins CI runs as a Windows Service, Test Studio requires the Java Web Archive version to run properly.

![Download Jenkins][1]

## Run the Jenkins Listener on a Custom Port

By default, the Jenkins Listener runs on port 8009 -- the same port as the Test Studio Scheduling Service. When installing the .war, use a command line argument to configure a different, non-conflicting port number for the listener (that is, avoid port numbers 8009, 8010, 8011, 8012, and 8013). For example:

```
java -jar jenkins.war --ajp13Port=8019
```

> Optionally you can use the <a href="/advanced-topics/build-server/jenkins-ci-plugin" target="_blank">Jenkins Test Studio Plugin</a> to setup Jenkins

## Create a Free-style Software Project 

Create a job and select 'Build a free-style software project'.

![Free-style software project][2]

## Add a Windows Batch Command Build Step 

Under the 'Add build step menu,' select 'Execute Windows batch command'.

![Command build step][3]

## Input ArtOfTest.Runner Command to Execute Test

Under 'Execute Windows batch command', input the ArtOfTest.Runner command to execute your test or test list, including <a href="/features/test-runners/artoftest-runner" target="_blank">full path to ArtOfTest.Runner.exe and appropriate arguments</a>.

![Arguments][4]

Your test execution step is now ready to save and run.

## Attach the Results Files to the Job 

1.	Add "**out**" parameter in the batch command. It should point to the default jenkins workspace `C:\Users\[userName]\.jenkins\jobs\test\workspace\%JOB_NAME%%BUILD_NUMBER%` so the results files are outputted in a folder with an unique name (Job Name + Build Number).
	
	![Out parameter][9]

2. Add a post-build action of type "**Archive the artifacts**".

	![Archive the artifacts][10]

3. Type `${JOB_NAME}${BUILD_NUMBER}` in the "**Files to archive**" field so all the results files can be taken.

	![Files to archive][11]

4. After the build completion all the results files will be attached to it.

	![Files to archive][12]

5. Click **Build Artifacts** and download the files in a *.zip file (it will keep the folder structure) and open the **.aiiresult* file.

	![Save in zip file][13]

Your Jenkins CI build is now ready to run.

## Disclaimer

In case you are running Test Studio tests using <a href="http://www.donaldsimpson.co.uk/2011/10/06/jenkins-slave-nodes/" target="_blank">Jenkins slaves</a> you may experience the following exception:

The process is not running in 'Interactive Mode'! The 'DialogMonitor' has been disabled for this Browser.

```
TestExecuteProxy.ExecuteTest() : EXCEPTION! (see below)
Outer Exception Type: System.TimeoutException
Message: Wait for condition has timed out
HRESULT: 0x80131505 (Official ID (if app.) = COR_E_TIMEOUT, Error Bit = FAILED, Facility = FACILITY_URT, Code = 5381)
Call Stack:
at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo, Object target)
at ArtOfTest.Common.WaitSync.For&#91;T&#93;(Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)
at ArtOfTest.Common.WaitSync.For&#91;T&#93;(Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)
at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)
at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect,*<br>
*ProcessWindowStyle windowStyle, String arguments)
at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InitializeWeb(ExecutionEngineCreateParams initParams)
at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.CreateAndInitializeEngine(Test test, ExecutionEngineCreateParams cp)
at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)
```

The error is related to the fact that Jenkins slaves cannot be ran as service. This will cause the automation to fail with the above exception. In this case you should start Jenkins service headless.

__Example__:

```
java -jar slave.jar -jnlpurl http://$HOST:$PORT/computer/$SLAVEMACHINE/slave-agent.jnlp
```

or

```
javaws http://$HOST:$PORT/computer/$SLAVEMACHE/slave-agent.jnlp
```

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

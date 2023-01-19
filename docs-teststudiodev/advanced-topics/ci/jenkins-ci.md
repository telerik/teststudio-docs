---
title: Jenkins CI
page_title: Jenkins CI - Test Studio Dev Documentation
description: How tu run Test Studio Dev tests in Jenkins CI
position: 1
---
# Jenkins CI

Build and execute Test Studio tests in Jenkins CI by following these steps:

1.Install the Java Web Archive (.war) for Jenkins CI. Test Studio requires the Java Web Archive version to run properly. If Jenkins runs as a service, desktop actions for functional UI tests will fail (there is no desktop interaction).

2.Create a free-style software project. Create a job and select 'Build a free-style software project'.

![Free-style software project][1]

3.Add a Windows batch command build step. Under the 'Add build step menu,' select 'Execute Windows batch command'. You can also use any other valid way that will allow you to start a windows process.

![Command build step][2]

4.Input ArtOfTest.Runner command line command to execute tests. Under 'Execute Windows batch command', input the ArtOfTest.Runner command to execute your test or test list, including <a href="/features/cli-runner" target="_blank">full path to ArtOfTest.Runner.exe and appropriate arguments</a>.

![Arguments][3]

Your test execution step is now ready to save and run.

## Attach the results files to the Job

1.Add "**out**" parameter in the batch command. It should point to the defaultrkspace **(%WORKSPACE%\%JOB_NAME%%BUILD_NUMBER%**) so the results files are outputted in a folder with an unique name (Job Name + Build Number) and set the result output to be in junit format.

![Out parameter][4]

2.Add a post-build action of type "**Archive the artifacts**".

![Archive the artifacts][5]

3.Type *${JOB_NAME}${BUILD_NUMBER}\\*** in the "**Files to archive**" field so all the results files can be taken.

![Files to archive][6]

4.After the build completion all the results files will be attached to it.

![Files to archive][7]

5.Click **Build Artifacts** and download the files in a *.zip file (it will keep the folder structure) and open the **.aiiresult* file.

![Save in zip file][8]

6.You can also review a result summary directly from the build page (if there are junit formatted results).

![Check the junit results][9]

Your Jenkins CI build is now ready to run.

**Disclaimer**:

In case you are running Test Studio tests using <a href="http://www.donaldsimpson.co.uk/2011/10/06ave-nodes/" target="_blank">Jenkins slaves</a> you may experience the following exception:

**Exception: The process is not running in 'Interactive Mode'! The 'DialogMonitor' has been disabled for this Browser.**

The problem is that if the Jenkins slave is running as a service, desktop interaction won't work. The Jenkins slave agent should instead run as a java app from the perspective of a user with an active user session.

Example:

**java -jar slave.jar -jnlpurl http://$HOST:$PORT/computer/$SLAVEMACHINE/slave-agent.jnlp**

or

**javaws http://$HOST:$PORT/computer/$SLAVEMACHE/slave-agent.jnlp**

[1]: images/fig2.png
[2]: images/fig3.png
[3]: images/fig4.png
[4]: images/fig9.png
[5]: images/fig10.png
[6]: images/fig11.png
[7]: images/fig12.png
[8]: images/fig13.png
[9]: images/fig14.png

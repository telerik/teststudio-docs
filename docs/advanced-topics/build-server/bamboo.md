---
title: Bamboo CI

page_title: Bamboo Test Studio Tests Integration
description: "Integrate Test Studio tests in bamboo continuous integration. Execute Test Studio tests with Bamboo"
position: 8
---
# Executing Test Studio Tests with Bamboo

<a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> test project can be integrated in continuous integration environment using Bamboo server.

**Using the ArtOfTest.Runner.exe**

In order to use ArtOfTestRunner.exe for executing your tests you will need to define new plan.

1.&nbsp; Create new plan

![Create new plan][1]

2.&nbsp; Configure the plan

![Configure the plan][2]

3.&nbsp; Add tasks

* 3.1.&nbsp; Add new command task:

![Add new command task][3]

First step is to add new executable, it's path should be path to the Test Studio runner (ArtOfTest.Runner.exe). **Default location of ArtOfTest.Runner.exe is "C:\Program Files (x86)\Progress\Test Studio\Bin".**

![Add new executable][4]

To configure the task add following arguments:

```
list="PATH_TO_PROJECT\TEST_LIST_NAME.aiilist" out=${bamboo.build.working.directory} junitstep
```

**OR**

```
test="PATH_TO_PROJECT\TEST_NAME.tstest" out=$bamboo.build.working.directory} junitstep
```

![Command task][5]

* 3.2 Add new script task - Convert to NO-BOM task

> Note: This task should be "Final task"

![New script task][6]

> This step is needed, because Bamboo JUnit parser can't parse files encoded in UTF-8-BOM. <br>
><br>
> Reference on the topic can be found <a href="https://confluence.atlassian.com/bamkb/junit-parser-failing-to-find-or-parse-test-results-935372076.html" target="_blank">here</a>.

Source of the script:

```
Write-Output $env:WORKDIR;

Get-ChildItem $env:WORKDIR -Filter *.xml | 
Foreach-Object {
    $MyFile = Get-Content $_.FullName
    Write-Output $_.FullName;
    $Utf8NoBomEncoding = New-Object System.Text.UTF8Encoding($False)
    [System.IO.File]::WriteAllLines($_.FullName, $MyFile, $Utf8NoBomEncoding)
}
```

Save the script in desired location.
Add following Environment variable to the task:

```
WORKDIR=${bamboo.build.working.directory}
```

![Script config][7]

* 3.3 Add new JUnit parser task

>Note: "This task should be Final task"

![JUnit parser task][8]

Specify custom results directories to be **/*.xml

![JUnit config][9]

[1]: /img/advanced-topics/build-server/bamboo/Create_plan.png
[2]: /img/advanced-topics/build-server/bamboo/Configure_plan.png
[3]: /img/advanced-topics/build-server/bamboo/New_command_task.png
[4]: /img/advanced-topics/build-server/bamboo/Add_new_executable-TestStudio.png
[5]: /img/advanced-topics/build-server/bamboo/Runner_command_task.png
[6]: /img/advanced-topics/build-server/bamboo/New_script_task.png
[7]: /img/advanced-topics/build-server/bamboo/Script_config.png
[8]: /img/advanced-topics/build-server/bamboo/New_JUnit_parser_task.png
[9]: /img/advanced-topics/build-server/bamboo/JUnit_config.png

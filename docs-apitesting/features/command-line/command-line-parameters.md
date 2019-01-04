---
title: Command Line Parameters
page_title: Command Line Parameters
description: "Progress® Test Studio® for APIs - Command Line Parameters"
position: 1
publish: true
---
# Command Line Parameters

## Options

Run `Telerik.ApiTesting.Runner --help` to view a list with all available commands.

Here is the Help Screen for Telerik.ApiTesting.Runner.exe:

![Options][1]

Currently `test` is the only supported command. See below for more information on how you can use it to run your project or tests.

## Test Options

Run `Telerik.ApiTesting.Runner test --help` to view a list with all available options for the `test` command.

Here is the Help Screen for Telerik.ApiTesting.Runner.exe test option:

Usage: `Telerik.ApiTesting.Runner test [options]`

Options:

  - `-?|-h|--help     Show help information`

  - `-p|--project     Project path`

  - `-v|--variable    Specify test parameters key=value`

  - `-t|--test        Test key to run`

  - `-s|--suite       Test suite (folder) to run`

  - `-f|--format      The format of the test results. Can be: 'xml', 'junit', 'junitstep'. Default is 'xml'`

  - `-o|--output      The path of the generated test results file`

  - `--start-from     Specifies the Key of the starting Step in a Test execution cycle`

  - `--stop-after     Specifies the Key of a Step that, once completed, will break the Test execution cycle`

### Examples

Here are several examples for command line commands to execute tests with the command line interface of Test Studio for APIs. Note that in the examples we call the runner with its default path `"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe"`. If you have it installed in a different location, you should change that path accordingly or use some of the other options described <a href="/features/command-line/overview">here</a>. The paths used in the commands to projects or tests are also examples and you should change them accordingly too.

  - To simply run an entire project:

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests"`

  - To run a project and set a couple of project-level variables:

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -v base-url=http://localhost:5000 -v user-name="John Smith"`

  - To run a single test:

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -t ".\CRUD Tests\Get All Users"`
  
  - To run a suite (folder):

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -s ".\CRUD Tests"`

  - To run more than one specific tests, list each one of them with a separate `-t` option:

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -t ".\Get User Id By Its Username" -t ".\CRUD Tests\Get All Users"`

  - To run a project, output test results in a specific location, and set their format to JUnit:

    `C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -o "C:\TestResults\result.xml" -f junit`


## Execution Options

Execution options modify command line test execution behavior. 
The help file (displayed by inputting Telerik.ApiTesting.Runner.exe --help from the command line) provides a brief explanation of each option. Here are some further notes about specific options.

Several execution options use file paths as values. When using file paths in the command prompt:  

- Enclose the file path in double quotes.
- To prevent typing mistakes, use the clipboard paste option within the command prompt window. To find the paste option after copying the path to the clipboard, right mouse click on the top left corner of the command prompt and choose **Edit > Paste**.

## Exit Codes

Telerik.ApiTesting.Runner.exe returns an exit code so the Build Server can check for it on process exit in case of an exception:
 * Exit code **0** - Run is processed and all tests passed.
 * Exit code **> 0** - Run is processed and some tests failed.

[1]: /img/features/command-line/apitesting-runner-help.png
---
title: Command Line Runner 
page_title: Command Line Runner | Test Studio Dev Documentation
description: Command Line Runner for Test Studio Dev tests
position: 10
---
# Command Line Runner

The ArtOfTest.Runner.exe is the command line runner for __Test Studio Dev__ tests and is installed in the Bin folder under the installation directory of the product. The default location is:

- **C:\Program Files (x86)\Progress\Test Studio**

When working with the execution engine in the command prompt always make sure you have started it as Administrator and have the root directory in context as shown below so that you can call the runner directly.

![cmd][1]

## Options

Here is the Help Screen for ArtOfTest.Runner.exe:

![Options][2]

## Execution Options

Execution options modify command line test execution behavior. The help screen (displayed by inputting ArtOfTest.Runner.exe -help from the command line) provides a brief explanation of each option. Here are some further notes about specific options.

Several execution options use file paths as values. When using file paths in the command prompt:

- Enclose the file path in double quotes.
- To prevent typing mistakes, use the clipboard paste option within the command prompt window. To find the paste option after copying the path to the clipboard, right mouse click on the top left corner of the command prompt and choose **Edit > Paste**.

![Edit>Paste][3]

- The **test** option takes the full path to an individual test file with the **.tstest** file extension. This file will be located in your main project directory and under any folder structure you have created to organize your tests. You can use the **test** option by itself. By default results will be stored in the **Results** folder under the project’s root directory.

<table id="no-table">
<tr>
<td>![Test Execution Syntax][4]<br>ArtOfTest.Runner Test Execution syntax</td>
</tr>
<tr>
<td>![Test Execution Result][5]<br>ArtOfTest.Runner Test Execution result</td>
</tr>
<table>

- The **list** option is currently not supported in Test Studio Dev Edition.
- The **out** option allows choice of an alternative folder to store the results to and takes a full path value to the respective folder.
- The **result** option allows change of the default result file name and takes file name (including the file extension and in double quotes).
- If any of the **xml** or **html** options are used the respective alternative result file will be stored to the default location if an output folder is not specified.
- If any of the **junit** or **junitstep** options is used a JUnit xml result file will be generated. The difference will be respectively whether to convert a test or a test step to a junit test.
- The **PersistOnEachStep** option could be set to true in case explicitly the results are required. This option will save the results after each executed step.
- The **settings** option takes the full path to a settings file with the **.xml** file extension.

## Exit Codes

ArtOfTest.Runner returns an exit code so the Build Server can check for it on process exit in case of an exception:

<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
}
table.docs th {
color:#fff;
background-color:#00аб8е;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>
<table class="docs">
<tr>
	<th>Code</th><th>Title</th><th>Summary</th>
</tr>
<tr>
	<td>**0**</td><td>RUN_TESTS_SUCCESS </td><td>Run is processed and all tests passed.</td>
</tr>
<tr>
	<td>**1**</td><td>RUN_TESTS_ERROR</td><td>Run is processed and some tests failed.</td>
</tr>
<tr>
	<td>**2**</td><td>NOT_RUN_UNEXPECTED_ERROR</td><td>Run is not processed due to unexpected error.</td>
</tr>
<tr>
	<td>**3**</td><td>NOT_RUN_COMPILATION_ERROR</td><td>Run is not processed due to compilation errors.</td>
</tr>
<tr>
	<td>**10**</td><td>NOT_RUN_USAGE_INFO</td><td>No run to process, requested usage info.</td>
</tr>
<tr>
	<td>**11**</td><td>NOT_RUN_INVALID_COMMAND_ARGS</td><td>No run to process due to general invalid arguments error.</td>
</tr>
<tr>
	<td>**12**</td><td>NOT_RUN_TEST_NOT_FOUND</td><td>Run is not processed due to invalid test path argument.</td>
</tr>
<tr>
	<td>**13**</td><td>NOT_RUN_TESTLIST_NOT_FOUND</td><td>Run is not processed due to invalid test list path argument.</td>
</tr>
<table>

[1]: images/artoftest-runner/fig1.png
[2]: images/artoftest-runner/fig2.png
[3]: images/artoftest-runner/fig3.png
[4]: images/artoftest-runner/fig4.png
[5]: images/artoftest-runner/fig5.png
[6]: images/artoftest-runner/fig6.png
[7]: images/artoftest-runner/fig7.png
[8]: images/artoftest-runner/fig8.png
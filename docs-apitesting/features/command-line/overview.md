---
title: Overview
page_title: Overview
description: "Progress® Test Studio® for APIs - Command Line Interface - Overview"
position: 0
published: true
---
# Command Line Interface - Overview

Test Studio for APIs provides a Command Line Interface application (Telerik.ApiTesting.Runner.exe) that you can use to directly execute an existing test project without using the application's user interface.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

<br>
The Telerik.ApiTesting.Runner.exe is installed in your <a href="http://www.telerik.com/teststudio">Test Studio</a> installation directory. 
According to the Test Studio edition that you have, the default location is:

 * Test Studio for APIs standalone Installer: **C:\Program Files\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole**
 * TestStudio Ultimate: **C:\Program Files\Telerik\Test Studio\Bin\ApiTesting\runnerconsole**

When working with the execution engine in the command prompt, make sure you are always running as Administrator to avoid issues related to lack of permissions to read/write the project and results files.

To execute the Telerik.ApiTesting.Runner.exe from command prompt you should do either:
  - Have the root directory in context so that you can call the runner directly - e.g.:
  
`C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole>Telerik.ApiTesting.Runner.exe`
  
  - Run from another location but specify the full path to the executable - e.g.:
  
`C:\>"C:\Program Files (x86)\Telerik\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe"`

  - Finally, you can add the path to the Telerik.ApiTesting.Runner.exe in your system PATH environment variable (Windows Control Panel >> System and Security >> System >> Advanced system settings >> Environment Variables >> System variables) so that you can execute directly from any location - e.g.:
  
`C:\>Telerik.ApiTesting.Runner`


See full list of <a href="/features/command-line/command-line-parameters">command line parameters</a>
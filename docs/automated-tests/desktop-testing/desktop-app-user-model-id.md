---
title: Application User Model ID
page_title: Application User Model ID
description: "Testing a desktop app with Test Studio using Application User Model ID. Use application user model id to configure desktop test for automating Windows store, UWP or Maui-based apps."
position: 3
---
# Use Application User Model ID for Test Studio Desktop Tests

Modern desktop applications often use alternative methods for starting and maintaining their processes. Desktop apps such as Windows store, UWP or Maui-based apps cannot be started from an executable file. For these Test Studio provides the option for automation using the Application User Model ID. 

Read below how you can find what is the User Model ID of the application you want to test. 

## List the Application User Model IDs

The <a href="https://docs.microsoft.com/en-us/windows/win32/shell/appids" target="_blank">Application User Model ID</a> is a unique identifier for an application in the OS. Follow the below steps to list the User Model IDs for all applicable applications installed on the computer. 

1.&nbsp; __Start PowerShell console using Admin rights__. Type _'PowerShell'_ in the Windows Start menu and choose the option _'Run as Administrator'_.

![Open admin PowerShell console](/img/automated-tests/desktop-testing/user-model-id/fig1.png)

2.&nbsp; __Copy the below script and paste__ it in the PowerShell console. Press __Enter__ to execute it.

```
$listOfAppUserModelIds = @()

foreach ($app in get-AppxPackage)
{
    try {
            if(-not $app.IsFramework){
				foreach ($id in (Get-AppxPackageManifest $app).package.applications.application.id)
				{
					$listOfAppUserModelIds += $app.packagefamilyname + "!" + $id
				}
			}
        }
        catch
        {
        }
}

$listOfAppUserModelIds
```
![Paste script in PowerShell console](/img/automated-tests/desktop-testing/user-model-id/fig2.png)

3.&nbsp; The script iterates through the installed applications and __outputs a list with their User Model ID__ - every app ID is on a new line. 

![Execute script in PowerShell console](/img/automated-tests/desktop-testing/user-model-id/fig3.png)

>__Note__
><br>
><br>
> The __application's ID is the whole string on the line__. Use the complete string with no additional or missing characters when <a href="/automated-tests/desktop-testing/desktop-test#configure-application-user-model-id" target="_blank">configuring the desktop test</a>.

## Filter List of User Model IDs

Usually the name of the application is part of the User Model ID and you can use it to __filter the output list from the script__. The parameter to use `| Select-String -Pattern 'nameOfTheApp'`  is added on the last line of the script where you need to specify the name of the application. Press __Enter__ to run it. 

Let's use the _Windows Calculator_ app as an example - the filter parameter for this application is `| Select-String -Pattern 'Calculator'` and is added on the last line.

```
$listOfAppUserModelIds = @()

foreach ($app in get-AppxPackage)
{
    try {
            if(-not $app.IsFramework){
				foreach ($id in (Get-AppxPackageManifest $app).package.applications.application.id)
				{
					$listOfAppUserModelIds += $app.packagefamilyname + "!" + $id
				}
			}
        }
        catch
        {
        }
}

$listOfAppUserModelIds | Select-String -Pattern 'Calculator'
```
![Filtered list of app ids in PowerShell console](/img/automated-tests/desktop-testing/user-model-id/fig4.png)

>__Note__
><br>
><br>
> You need to __replace the _Calculator_ value with the name of the application__ you look for. 
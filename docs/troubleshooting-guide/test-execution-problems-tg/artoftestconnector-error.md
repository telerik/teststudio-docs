---
title: RunDLL Error When Automating WPF App
page_title: RunDLL Error When Automating WPF App
description: Starting a WPF test recording or execution throws error 'There was a problem starting "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Connector_64.dll". The specified module could not be found.' and doesn't start the run. Testing a 64-bit WPF application throws error in Test Studio.
position: 1
---
# RunDLL Error When Automating 64-bit WPF Application

## Problem

I need to automate a 64-bit WPF application. When I try to configure a WPF test in Test Studio or run an existing one, I get a message that a dll is missing. If I check the listed directory I can see the file listed in it, but no test starts for the automated WPF application.

```
There was a problem starting C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Connector_64.dll. 
The specified module could not be found.
```

## Solution

The issue is related to some dependencies of Test Studio to C++ libraries, which might be missing on the machine and were not deployed with the installation of the tool. The issue is addressed with the development team and will be fixed.

Meanwhile you can __manually install the missing Microsoft redistributable libraries__ and continue using your WPF automation project. The latest supported <a href="https://docs.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2015-2017-2019-and-2022" target="_blank">Microsoft Visual C++ Redistributable packages are listed here</a>. choose the one corresponding to your environment and install it. Then Test Studio tests should start as expected.

---
title: Failed Internet Shortcut
page_title: Failed to Create Internet Shortcut
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Failed to Create Internet Shortcut


## PROBLEM

 You may experience an installation problem that is caused when Internet shortcuts are created in the Start Menu. If this is the case, you'll see a message in the install log like this:


*WixCreateInternetShortcuts: Creating IUniformResourceLocatorW shortcut 'C:\Documents and Settings\All Users\Start Menu\Programs\Telerik\Test Studio 20XX.X\Online Community Forums.url' target 'http://www.telerik.com/automated-testing-tools/community/forums.aspx'
WixCreateInternetShortcuts: Error 0x80040154: failed to save shortcut 'C:\Documents and Settings\All Users\Start Menu\Programs\Telerik\Test Studio 20XX.X\Online Community Forums.url'
WixCreateInternetShortcuts: Error 0x80040154: **failed to create Internet shortcut***

## SOLUTION

Run the installer from the command prompt that passes an argument to skip the Internet shortcut deployment. Here is the full command line:


**msiexec /i [MsiPackagePath] DISABLE_INTERNET_SHORTCUTS=1**

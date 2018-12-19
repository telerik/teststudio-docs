---
title: Getting Out of Memory Exception Errors
page_title: Getting Out of Memory Exception Errors
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/knowledge-base/oom.aspx
position: 1
---
#Dealing with OutOfMemoryException Errors#

##Problem##

When working with very large Test Studio test projects (350+ tests) or very large result sets you may get out of memory errors. Test Studio does not have any built-in hard limits on project size or results size. Naturally the larger the project or the larger the result set the more memory it will require. Test Studio, being a 32-bit Windows application, has an address space limitation of 2GB put upon it by the OS, no matter how much physical memory you actually have.

When a Windows application asks the OS for a block of memory, Windows will attempt to satisfy that memory request with a contiguous block of memory. If you ask for a 40MB block of memory, it means a single 40MB block of memory (not a piece from here and a piece from there). If Windows cannot find a contiguous block of memory large enough to satisfy the request and make it fit within the 2GB address space for the application, i.e. fit along with all the other memory the application is already using, you will get an OutOfMemoryException error from the OS and the application usually will be terminated by the OS.

##Solution##

###Option 1###

The most obvious option is to break up your test project or your tests into multiple smaller pieces. This way the memory being used will not be as great. Our experience shows that you will start to get out of memory errors with projects larger than about 350 tests total or with tests that have over 800 steps in them.

###Option 2###

Another option that sometimes helps is to use a 64-bit version of Windows. This version of Windows can handle more physical memory which allows it to better manage the memory it has and may more easily be able to satisfy requests for large blocks of memory.

###Option 3###

This last option is more experimental, but has been shown to work in a few cases. There is a flag called "LARGEADDRESSAWARE" that can be turned on for 32-bit executables like Test Studio. When this flag is set Windows will let the application use 3GB of address space instead of 2GB of address space. This flag only works when you're using a 64-bit version of Windows. It also requires Visual Studio to be installed before you can set this flag. To turn on this flag follow these 3 steps:

1.&nbsp; Open a Visual Studio command prompt (the standard command prompt won’t have the path set properly), with admin privileges

2.&nbsp; Enter “**cd C:\Program Files (x86)\Telerik\Test Studio\Bin**”

> Please note that as of version **2017 R3** the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

3.&nbsp; Enter “**editbin /LARGEADDRESSAWARE Telerik.TestStudio.Desktop.exe**”

That should be it. To double check that it worked, you can (in the same command prompt) run:

**dumpbin /headers Telerik.TestStudio.Desktop.exe**

You are looking for something ~12 lines down that says “Application can handle large (>2GB) addresses”

4.&nbsp; If you do not have editbin exe in the bin folder you can use <a href="http://www.techpowerup.com/forums/threads/large-address-aware.112556/" target="_blank">this</a> small tool.


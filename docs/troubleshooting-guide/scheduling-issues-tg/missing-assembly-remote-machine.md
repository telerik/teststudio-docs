---
title: Missing assembly reference on the remote machine
page_title: Missing assembly reference on the remote machine
description: "Missing assembly reference on the remote machine when running tests remotely via the Test Studio Scheduling setup."
position: 1
---
# Missing assembly reference on the remote machine

## PROBLEM

You are executing your test list locally just fine, however when executed through the scheduling on a remote machine you are getting compile errors that you have missing assembly reference and the the tests are not executed on the remote machine.

## SOLUTION

In case you add an external assembly reference in your project and try executing some of the test remotely prior the test execution the Test Studio compiler checks for available assembly path using the following methods:

1. In case of relative path - builds the full path combined between project root and the relative path as seen in the UI. So if the .DLL is added originally within the project, with respective relative path - this is the most secure way of the setup as the file structure will be persisted along with the project.

2. In case of missing path, checks whether the assembly is available in <a href="https://msdn.microsoft.com/en-us/library/yf1d93sz(v=vs.110).aspx" target="_blank">GAC</a> - this often fails unless the user has made sure the needed assembly (and it's dependencies if any) are GACed. 



Therefore we can recommend as a best practice **option 1** so that the user has no problem compiling the project on remote machines.

> It is important that once added within the project, the .DLL should be <a href="http://docs.telerik.com/teststudio/advanced-topics/coded-steps/add-assembly-reference" target="_blank">added to the project references</a> from there.

This all applies to the assembly reference dependencies (external assembly may depend on others).

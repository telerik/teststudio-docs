---
title: Keep an Active Session
page_title: Keep an Active Session
description: No Functional tests can be executed on locked machine or inactive desktop session. This is a possible solution how to configure few machines to keep an active session on one of the machines. 
position: 1
---
# Keep an Active Session Running on the Execution Server

Scheduling involves running Test Studio tests on an Execution Server. However, any test that requires moving the mouse or sending keystrokes requires an unlocked desktop. Test Studio tests are not the only ones affected by this Windows limitation. This is a general problem with any tool that performs UI testing.

Test Studio tests running against HTML-based web applications (ASP .NET and others) frequently can work on a locked machine because most test steps don't use the mouse or keyboard. Instead they are able to inject events (like a Click or Select) directly into the DOM structure of the page. Unfortunately, when performing WPF testing, these events cannot be injected in the same way. We have to simulate system-wide mouse moves and mouse clicks instead.

## Solution

Here is one possible solution to this challenge:

1. Prepare three machines, virtual or physical. One of these is your intended execution server. Let's call the three machines **A**, **B** and **C**. Let's say **B** is the intended Execution Server.

2. Start a **Remote Desktop Connection** on machine **C** and use it to log into **A**.

3. Once logged in, start a Remote Desktop Connection on A and use it to connect to **B**.

4. Once logged into **B**, remove the **Remote Desktop Connection** between **A** and **C**.

A **Remote Desktop Connection** remains open between **A** and **B**. This causes **B** to keep an active session. This allows you to use the machine as an Execution Server without human intervention.

![Active session][1]

* This is a stable solution based on how Windows treats remote sessions, and works on Windows Server 2003.

* This might not be as easy to implement on Windows Server 2008 & 7, depending on your company's security policy.

	* Check with your System Administrator if you suspect security limitations are preventing you from implementing this approach.

* If you are using the Windows Task Scheduler to create a task for ArtOfTest.Runner, you must select Run only when user is logged on in the scheduled task's properties:

![Create task][2]

[1]: /img/knowledge-base/scheduling-kb/keep-active-session/fig1.png
[2]: /img/knowledge-base/scheduling-kb/keep-active-session/fig2.png
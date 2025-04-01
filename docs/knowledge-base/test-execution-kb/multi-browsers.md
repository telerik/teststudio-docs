---
title: How to Run Tests in Parallel / in Multi Browsers
page_title: How to Run Tests in Parallel / in Multi Browsers
description: How can I run my tests in parallel? How do I run my tests in multiple browsers? Run scheduled Test Studio tests against different browsers.
position: 1
---
## How to Run Tests in Parallel / in Multi Browsers

Customers often wonder "How can I run my tests in parallel" and/or "How do I run my tests in multiple browsers, including multiple versions of the same browser". There are many ways to accomplish this. This article will focus on how to achieve this using the <a href="/features/scheduling-test-runs/Overview" target="_blank">Scheduling Server and Execution Server</a> that comes with both full Test Studio and our <a href="/general-information/test-studio-run-time" target="_blank">Runtime edition</a>.

No matter which approach you try to take, there are some restrictions to running tests in parallel that must be honored:

1. You can only run one Test Studio test at a time on a single machine. Test Studio tests are a type of UI testing. If multiple tests try to run in parallel on the same machine, the two windows (Browser or WPF application window) would be fighting each other for input focus control as well as mouse and keyboard control. One of the other will lose causing your tests to unexpectedly fail. Our scheduling server will limit you to running one test at a time for an individual machine.

2. Only one version of any specific browser can be installed and used to run a Test Studio test on a machine at a time. You might ask "What about IE compatibility mode"? There are two problems with trying to use compatibility mode. First Test Studio doesn't have a mechanism to set the compatibility mode and second compatibility mode doesn't actually change which version the browser is running as. It only does slight modifications to the UI rendering of a page. The core code of the browser will be the same, including the JavaScript runtime engine. Running IE in compatibility mode just isn't the same as actually running it on that version of IE. You can end up with false positives as well as false negatives when trying to "cheat" by using compatibility mode.

We've also heard that it's possible to have multiple versions of Firefox installed such that you can run a specific version of Firefox in a sandboxed process. Test Studio does not have support for a sandboxed Firefox process. It can only find and use the last normally installed version of Firefox as a standard Windows process.

You now may be wondering "With the above restrictions how is it possible to run tests in parallel"? The answer is it can be done, but it requires multiple machines. Each machine can be running a different test simultaneously. It is very common to use a set of virtual machines (VM's) for running your tests. You will need one machine for each unique version of a browser you want to run your test in. The good news is that you can have multiple browsers installed on the same machine and run your tests against different browsers on that machine.

For example, you want to run your tests in IE 9, 10, 11 as well as the latest version of Chrome and Firefox. This requires a minimum of three machines, one for IE 9, one for IE 10 and one for IE 11. You can also install Chrome and Firefox on any of the three machines, or all three if you like. Or if you prefer setup two additional machines, one for Chrome and one for Firefox.

## How to Run Tests in Multiple Browsers

Now let's get into the technical details of how to make your tests run in different browsers. First you must put your test or tests into a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a>. Next open the <a href="/getting-started/test-execution/test-list-settings" target="_blank">Test List Settings</a>, go to the Web tab and open the ExecutingBrowsers drop down.

![Multiple browsers][1]

Here is where you select which browser or browsers you want Test Studio to run that test list in. The default will run the test list in IE only. In this screen shot I've selected IE and Firefox and Chrome. At run time Test Studio will run the full test list from start to finish in IE, then it will run it again in Firefox and last it will run it again in Chrome. When finished you will see three different result sets in the <a href="/getting-started/test-results/analyze-test-results" target="_blank">Results view</a>, one result set for each browser the test was executed in.

That's all it takes to make your tests run in different browsers on the same machine.

## How to Run Tests in Parallel

As previously stated in this article, to run tests in parallel you must setup multiple execution servers. Here's a high level block diagram of what this looks like:

![Parallel execution][2]

You can have as many <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution Servers</a> setup and controlled by one <a href="/features/scheduling-test-runs/connect-to-scheduling-server" target="_blank">Scheduling Server</a> as you want. Of course each Execution Server requires that Test Studio is installed on it (one license per machine). We recommend installing our Runtime edition. It was specifically made for supporting this environment (and the cost for a Runtime license is a lot less than the cost for full Test Studio).

Once you have your scheduling and execution environment setup, you go to the Test List tab in Test Studio and select either Run List Remotely or Schedule Test List. In both cases you will be presented with a list of execution servers to run the test list on and an option "Distribute test among these machines".

First select which machines you want your tests executed on. You can select as many or as few as you like. Here's what "**Distribute test among these machines**" does:

* When checked the first test in the list will be handed to the first execution server. That server will run that test as soon as possible.
At the same time the second test in the list will be handled to the second execution server. That server will run the second test as soon as possible. You now have two tests running in parallel.
This process continues until all execution servers that you selected are running tests in parallel. The first execution server that finishes will be given the next test in the list to execute as soon as possible, and so on until all tests contained in the test list have been handed out to execution servers.

* When unchecked every execution server will be given the same test list. All execution servers will start with test one and continue until all tests in the test list have been executed. This mode is useful when you want all tests run in different versions of the same browser, such as IE 9, 10 and 11.

That's what it takes to get tests running in parallel using our Scheduling and Execution servers. As briefly mentioned above, there are other methods, but they all involve putting together your own home grown scheduling environment. Maybe you want to write your own specialized scheduling server that better fits the needs of your organization. Or maybe you'd prefer to use Microsoft Test Manager. This document will not explore those options. You may contact Test Studio technical support of you want to pursue other options.

[1]: /img/knowledge-base/test-execution-kb/multi-browsers/fig1.png
[2]: /img/knowledge-base/test-execution-kb/multi-browsers/fig2.png
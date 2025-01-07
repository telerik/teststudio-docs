---
title: Selecting Traffic
page_title: Selecting Traffic
description: Select the traffic in a load user profile for useful and robust load test results. 
position: 1
---
#Selecting Load Traffic

There are many types of load tests, each with its own goals. But for most load tests, following a few general principles should provide more useful and robust load test results.

##Simulate Realistic User Behavior

Once you have identified the expected ways in which users will interact with your application, you can use this information to simulate the load your application will encounter. Using <a href="/getting-started/create-test-standalone/web-test" target="_blank">Test Studio Web Tests</a>, you can record typical workflows in the browser then, you can <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">import these as Profiles</a> inside a Test Studio Load Test. Finally, you can <a href="/features/testing-types/load-testing/test-settings" target="_blank">allocate different percentages of the Workload</a> to each User Profile according to the percentage of users that you expect to perform this workflow. This way, your load test will generate traffic that accurately simulates your expected users


##Record Cross-Browser Traffic

Different browsers generate different kinds of traffic. To simulate this variety, <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">record your load traffic in a variety of browsers</a> that reflects your specific users or the broader Internet usage. You can <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">capture your load traffic from functional tests in a variety of browsers</a>. Or, you can capture traffic in your load test directly and select the proper browsers. Once you have recorded the User Profile, you can allocate Workload based on the popularity of the browser.


##Test Components Separately

In addition to testing the overall mix of user workflows, you can also create separate load tests that only focus on a specific part of your application (for example, the login workflow). This will provide information about which components suffer the greatest performance decrease under stress. This is especially useful once you have determined that your application is not meeting expectations and wish to identify the performance bottleneck. It also helps to fine-tune the performance of an application that already meets requirements.


##Functional, Performance, and Load

To save time and increase accuracy, begin with functional tests (like Web Tests) to ensure your application behaves correctly; then, use these to create <a href="/features/testing-types/performance-testing/overview" target="_blank">Performance tests</a> to see the experience of a single user and find performance issues that occur without load. Finally, import your functional tests into Load tests to see the behavior of the application with large numbers of users. Repeat these tests throughout the development process to prevent regressions and identify opportunities for performance improvements.

##See Also

* <a href="/knowledge-base/load-testing-kb/load-strategies" target="_blank">Load Testing Strategies</a>

* <a href="http://www.telerik.com/whitepapers/teststudio/taking-the-first-steps-in-web-load-testing" target="_blank">"Taking the First Steps in Web Load Testing" white paper</a>
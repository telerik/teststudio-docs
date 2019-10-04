---
title: Best Practices 
page_title: Best Practices for Load Test List Run
description: "Test Studio Best Practices in load test execution. What is recommended to keep in mind when running load tests in Test Studio locally or using multiple machines."
position: 2
---
# Best Practices

To get the most out of your Load Test it is best if you follow few simple guidelines.

## Local Load Test Run

<a href="/features/testing-types/load-testing/running-load-test/running-tests" target="_blank">Executing load test locally</a> is often used while designing a user profile to execute valid HTTP requests. To get the most out of such run, there are few recommendations to keep in mind:

- Use a small amount of users - even one user is sufficient to follow up which of the requests are really executed.

- Use short time to run the test - the minimum time you can use is a minute and this is usually sufficient for all requests in a user profile to be executed.

- Use <a href="https://www.telerik.com/fiddler" target="_blank">Fiddler</a> to capture the traffic generated from the test run - that way you can follow up which are the successfully executed HTTP calls and if their responses are the expected.

- Use the <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">Test Studio application log</a> to find out what is the missing piece - the application log of Test Studio also records all actions while working within the tool. In a log, generated during a load test run, you can find see the executed HTTP requests.

- Collaborate with the application under test development team - nowadays web applications are complex and can be built with plenty of different technologies. If you need to load test a web page, you are not familiar in details with, it will be helpful to initiate a discussion with the development team about load testing with Test Studio. Certainly the developers of the application will be able to share specific information about the page and application server. 

## Remote Load Test List Run

Follow the below recommendations to prepare a <a href="/features/testing-types/load-testing/running-load-test/remote-load-test-execution" target="_blank">load test to be executed on multiple machines</a>.

- Make sure you have think times with deviations. Think Times with deviations have a random duration. By having some users at different intervals sitting out of the test (thinking) it not only mimics real world usage better, but it allows for your agents I/O to not be as congested. It may be counter intuitive, but having your virtual users stop to think for a time will actually increase the number of users and requests that your agent can complete.

- Use ramp times to build up your users from a small number to larger numbers. Again, if you start with a large consistent load, without any ramping, you will likely clog the I/O. By ramping up from lower numbers you give your think times better chances to get involved.

- Use more CPUs, Test Studio Load Agents are multi-threaded, so take advantage of that by giving more CPUs to your agents to increase throughput. In general approximately 8 users per CPU unit seems to be sufficient to have a realistic load testing results.

- Use more Agents. The more agent machines you use, the more networking ports you can use at any one time, freeing up congestion on the agent side.

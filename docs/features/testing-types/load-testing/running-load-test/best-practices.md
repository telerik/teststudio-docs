---
title: Best Practices
page_title: Best Practices
description: "Test Studio Best Practices in load testing "
position: 2
---
# Best Practices

To get the most out of your Load Test it is best if you follow a few simple guidelines:

- Make sure you have think times with deviations. Think Times with deviations have a random duration. By having some users at different intervals sitting out of the test (thinking) it not only mimics real world usage better, but it allows for your agents I/O to not be as congested. It may be counter intuitive, but having your virtual users stop to think for a time will actually increase the number of users and requests that your agent can complete.

- Use ramp times to build up your users from a small number to larger numbers. Again, if you start with a large consistent load, without any ramping, you will likely clog the I/O. By ramping up from lower numbers you give your think times better chances to get involved.

- Use more CPUs, Test Studio Load Agents are multi-threaded, so take advantage of that by giving more CPUs to your agents to increase throughput. In general approximately 8 users per CPU unit seems to be sufficient to have a realistic load testing results.

- Use more Agents. The more agent machines you use, the more networking ports you can use at any one time, freeing up congestion on the agent side.

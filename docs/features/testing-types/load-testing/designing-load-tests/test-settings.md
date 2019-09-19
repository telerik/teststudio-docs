---
title: Load Test Settings
page_title: Load Test Settings
description: "Load Test Settings in Test Studio - User Profile Name, Workload, Available Users, Time"
position: 4
---
# Load Test Settings

Each load test in Test Studio can be configured to use different amount of virtual users and different time to run. Along with that you need to adjust the workload between the different profiles (if more than one in the test).

## Workload

In the Test Studio load test can be added multiple <a href="/features/testing-types/load-testing/designing-load-tests/adding-user-profiles" target="_blank">user profiles</a>. That way you can simulate multiple users performing different scenarios against the application under test. To be even more precise, when testing the page, you can control the virtual user distribution between the different profiles - you may not want all the HTTP traffic hitting the page equally, so you may configure some of the user profiles to be much more frequent than other. 

This setting is called __Workload__ and this is the percentage of virtual users used for a User Profile compared to all the User Profiles included in the test. Set the percentage with the Workload slider in the _Design_ section of a load test.

![Workload][3]

**See Also:** <a href="/knowledge-base/load-testing-kb/virtual-users" target="_blank">Workload and the concept of Virtual Users in Test Studio</a>

## Available Users and Time Settings

In the _Available Users_ section, you can specify how many concurrent VUs to use during the load test. Depending on the type of testing you need to perform, you can use different amounts of users and times to ramp up these.

![Available users and time settings][4]

**See Also:** <a href="/knowledge-base/load-testing-kb/load-strategies" target="_blank">Load Strategies</a>

### Users to Start and End with

Specify the amount of users to start and end the load test run. Depending on the scenario, the amount can be increasing, decreasing or constant.

![Users to use during the run][4a]

### Time

Specify the _Ramp Up_ time and the total load test duration. The _Ramp Up_ time is the amount of time to gradually increase or decrease the total concurrent VUs using the values set for _Start Users_ and _End Users_.

![Ramp Time][5]

> The _Ramp Up_ time cannot exceed the total time to run the test and will not be applied for the test run, if the virtual users amount is constant.

### Users Over Time Graph

Any changes in the Test Settings will appear in the _Users Over Time_ graph.

![Time Graph][6]

[1]: /img/features/testing-types/load-testing/test-settings/fig1.png
[2]: /img/features/testing-types/load-testing/test-settings/fig2.png
[3]: /img/features/testing-types/load-testing/test-settings/fig3.png
[4]: /img/features/testing-types/load-testing/test-settings/fig4.png
[4a]: /img/features/testing-types/load-testing/test-settings/fig4a.png
[5]: /img/features/testing-types/load-testing/test-settings/fig5.png
[6]: /img/features/testing-types/load-testing/test-settings/fig6.png

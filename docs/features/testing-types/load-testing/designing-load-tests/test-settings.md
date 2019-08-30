---
title: Test Settings
page_title: Load Test Settings
description: "Load Test Settings in Test Studio - User Profile Name, Workload, Available Users, Time"
position: 4
---
# Test Settings

Each load test in Test Studio can be configured to use different amount of virtual users and different time to run. Along with that you need to adjust the workload between the different profiles (if more than one in the profile).

## Workload

The <a href="/knowledge-base/load-testing-kb/virtual-users" target="_blank">Workload</a> is the percentage that each User Profile will be used compared to all the User Profiles contained in the test. Set the Workload with the Workload slider.

Configure the work load distribution of your user profiles. You may not want all the HTTP traffic hitting your application under test equally. You may configure some of the user profiles to be much more frequent than the other user profiles.

![Workload][3]

## Available Users

In the Available Users fields, specify how many concurrent VUs to use at the beginning and end of the Load Test.

![Available users][4]

## Time

Specify the Ramp Up time and the total Load Test duration (Figure 4). The ramp up time is the amount of time to gradually increase the total VUs from the Start Users setting to the End Users setting.

![Ramp Time][5]

Each of your Test Settings will appear in the Users Over Time graph.

![Time Graph][6]

**See Also:**

- <a href="/knowledge-base/load-testing-kb/virtual-users" target="_blank">Virtual Users Knowledge Base article</a>
- <a href="/knowledge-base/load-testing-kb/load-strategies" target="_blank">Load Strategies</a> 

[1]: /img/features/testing-types/load-testing/test-settings/fig1.png
[2]: /img/features/testing-types/load-testing/test-settings/fig2.png
[3]: /img/features/testing-types/load-testing/test-settings/fig3.png
[4]: /img/features/testing-types/load-testing/test-settings/fig4.png
[5]: /img/features/testing-types/load-testing/test-settings/fig5.png
[6]: /img/features/testing-types/load-testing/test-settings/fig6.png



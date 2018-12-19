---
title: Capturing Traffic
page_title: Capturing Traffic
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 5
---
# Capturing Traffic

Click ![Camera][1] to open the Capture Traffic dialog. Before making a selection, close all browser instances as well as any other applications that may generate HTTP traffic, so that the user profile does not include extra HTTP traffic. 

![Capture Traffic][2]

This opens the **Capture Traffic** dialog. Choose whether to capture traffic from a Test Studio Web Test or capture new traffic.

![Capture Traffic Dialog][3]

If you choose **Capture from existing web test**, select the existing web test from the grid that appears. Next, select a specific browser to launch to capture the traffic. Only traffic from this browser will be captured.
Or, select a device to capture traffic from. Capturing from a remote source requires you to <a href="/features/testing-types/load-testing/configure-remote-device" target="blank">configure that device to use the remote proxy</a>.

If you selected **Capture New**: 

1.&nbsp; Record your web browser session.

2.&nbsp; Close the browser.

3.&nbsp; Click **Stop Recording**.

Next, customize the new user profile. You can return to these screens later. 

- Select <a href="/features/testing-types/load-testing/dynamic-targets" target="_blank">Dynamic Targets</a> if needed.
- Edit the <a href="/features/testing-types/load-testing/modifying-tests" target="_blank">captured traffic</a> or add <a href="/features/testing-types/load-testing/think-times" target="_blank">think times</a>.
- Click **Save**.


[1]: /img/features/testing-types/load-testing/capturing-traffic/fig1.png
[2]: /img/features/testing-types/load-testing/capturing-traffic/fig2.png
[3]: /img/features/testing-types/load-testing/capturing-traffic/fig3.png


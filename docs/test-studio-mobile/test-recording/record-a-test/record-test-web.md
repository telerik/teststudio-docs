---
title: Record Web Test
page_title:  Record Web Test
description: "Record a Test Studio Mobile test"
publish: true
position: 2
slug: ms-record-test-web
---

> Although the Mobile testing module is in the process of discontinuation, Test Studio main product continues supporting <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">responsive testing of web applications</a> to help meeting the demand of mobile users.
><br>
><br>
> Read <a href="/automated-tests/responsive/responsive-test" target="_blank">here technical documentation for web responsive testing</a> in Test Studio.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

#Record a Web Test

Once the web agent (browser) is [connected]({% slug ms-connect-webagent%}) to Test Studio Mobile the agents (browsers) are listed in the **Conencted Devices** pane.

1. [Create]({% slug ms-create-test%}) and open a Web test. Once you open it the recording buttons are getting enabled.

	![Record buttons](/img/test-studio-mobile/test-recording/record-test/record-web-test/fig1.png)

2. Clicking on any of the **Record** buttons shows a dialog where *Application Url* must be typed (e.g. http://www.telerik.com).

	![Set URL](/img/test-studio-mobile/test-recording/record-test/record-web-test/fig2.png)

3. Clicking the **Start** button navigates to the set URL in your mobile browser. The test recorder is attached and any gestures or actions you perform over the launched web application is recorded as steps in the Test Studio test. 

	![Record the test](/img/test-studio-mobile/test-recording/record-test/record-web-test/fig3.png)

	**Note:** Additional steps (e.g. verifications) can be added through the [Step Builder]({% slug ms-step-builder%}).

4. Once the test is complete, stop recording by clicking on the **Stop Record** button. The recorder is detached and you can run the test.

	![Stop the recording](/img/test-studio-mobile/test-recording/record-test/record-web-test/fig4.png)

## See also

* [Connect a Web Agent]({% slug ms-connect-webagent%})
* [Step Builder]({% slug ms-step-builder%})
* [Quick Execution]({% slug ms-quick-execution%})

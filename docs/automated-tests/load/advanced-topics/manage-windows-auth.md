---
title: Manage Windows Authentication
page_title: Manage Windows Authentication
description: "Manage Windows Authentication in Test Studio load test. The tested application supports Windows Authentication - can use that in Test Studio load test"
position: 0
publish: false
---
# Manage Windows Authentication

If the target application supports Windows Authentication, you can configure your load test to connect using a Windows Authentication identity.

To enable the user profiles in a load test to use Windows authentication and customize their identity, click the ___Manage Windows Authentication___ button in the load test ___Design___ view.

![Manage Windows Authentication][2]

In the ___Manage Windows Authentication___ window click ___Add Identity___ to configure a new Windows Authentication identity.

![Create new Win Auth Identity][3]

1.&nbsp; A friendly name to refer to this Windows Authentication identity;

2.&nbsp; The domain name for this identity;

3.&nbsp; The username for this identity;

4.&nbsp; The password for this identity;

5.&nbsp; Click the ___Save___ button to store the new identity details to the authentication options for your load test user profiles.

> __Note!__ The password saved for a Windows Authentication identity is not encrypted for storage or display. The password will be displayed in plain text in the ___Manage Windows Authentication___ window. To reduce security risks, use test accounts to authenticate your load tests.

To allow a user profile to use a ___Windows Authentication Identity___, select the respective Identity Name from the ___User Identity___ drop-down menu for that user profile.

![Select identity for a user profile][4]

> __Note!__ When using __Windows Authentication__, it is normal for your load test results to include a high number of 401 responses. This is because Test Studio opens a new connection after executing each user profile.

If your test is <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">bound to a data source</a>, you can select a data source column to bind to the ___Windows Authentication Identity___ fields.

![Bind Win Auth][5]

[1]: /img/features/testing-types/load-testing/manage-windows-auth/fig1.png
[2]: /img/features/testing-types/load-testing/manage-windows-auth/fig2.png
[3]: /img/features/testing-types/load-testing/manage-windows-auth/fig3.png
[4]: /img/features/testing-types/load-testing/manage-windows-auth/fig4.png
[5]: /img/features/testing-types/load-testing/manage-windows-auth/fig5.png

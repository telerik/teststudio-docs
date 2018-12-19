---
title: Manage Windows Authentication
page_title: Manage Windows Authentication
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 16
---
# Manage Windows Authentication

If the target application supports Windows Authentication, you can configure your load test to connect using a Windows Authentication identity. To enable your profiles to use Windows authentication and customize their identity, click ![Manage Windows Authentication button][1].

![Manage Auth][2]

Click ‘Add Identity’ to configure a new Windows Authentication identity. Enter:

1.&nbsp; A name to refer to this Windows Authentication identity;

2.&nbsp; The domain name for this identity;

3.&nbsp; The username for this identity;

4.&nbsp; The password for this identity.

![Manage Win Auth][3]

> Important: The password saved for a Windows Authentication identity is not encrypted for storage or display. The password will display in plain text in the ‘Manage Windows Authentication’ window. To reduce security risks, use test accounts to authenticate your load tests.

Click ‘Save’ to add this identity to the authentication options for your load test user profiles.
To configure a user profile to use a Windows Authentication Identity, select the Identity Name from the User Identity drop-down menu for that user profile.

![New Auth][4]

>  When using Windows Authentication, it is normal for your load test results to include a high number of 401 responses. This is because Test Studio opens a new connection after executing each user profile.

If your test is <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">bound to a data source</a>, you can select a data source column to bind to the Windows Authentication Identity fields.

![Bind Win Auth][5]

[1]: /img/features/testing-types/load-testing/manage-windows-auth/fig1.png
[2]: /img/features/testing-types/load-testing/manage-windows-auth/fig2.png
[3]: /img/features/testing-types/load-testing/manage-windows-auth/fig3.png
[4]: /img/features/testing-types/load-testing/manage-windows-auth/fig4.png
[5]: /img/features/testing-types/load-testing/manage-windows-auth/fig5.png

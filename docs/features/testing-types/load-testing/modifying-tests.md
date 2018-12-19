---
title: Modifying Tests
page_title: Modifying Tests
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 12
---
# Modifying Tests

Tests can be modified in a number of ways:


- Add/Remove user profiles
- Change the test settings (number of virtual users, the duration of the test, the workload)
- Change the user profile name
- Add/Remove/Change the think times
- Modify the HTTP transactions

## Add/Remove User Profiles

To add a new user profile either <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">capture new traffic</a> or <a href="/features/testing-types/load-testing/importing-traffic" target="_blank">import new traffic</a>. To remove a user profile click ![Delete][1] on the row of the user profile you want to delete.

> Once deleted that user profile is permanently removed. You cannot undo this delete.

![Delete button][2]

## Change the Test Settings

You can change any of the <a href="/features/testing-types/load-testing/test-settings" target="_blank">test settings</a>, such as number of virtual users, the duration of the test, or the workload balance by simply opening the test and adjusting the desired setting.

## Change the User Profile Name 

To change the name of a user profile:

1.&nbsp; Open the desired test.

2.&nbsp; Click ![Edit][3] next to the user profile you want to change. 

![Edit button][4]

3.&nbsp; This will open that user profile. Type in the new name at the top. 

![Name][5]

4.&nbsp; Click **Save**.

## Add/Remove/Change the Think Times

To modify the think times of a user profile: 

1.&nbsp; Open the user profile you want to modify just like you were going to modify the user profile name.

2.&nbsp; Adjust the <a href="/features/testing-types/load-testing/think-times" target="_blank">think times</a> as needed.

## Modifying HTTP Transactions

The contents of the HTTP requests that will be sent to the website under test that are contained in a user profile can be modified. Only the contents of the existing headers can be modified. You cannot add/delete headers of an existing transaction. Also you cannot modify the expected response since this will come from the website under test, not sent to the website.

> This should only be attempted by someone who is an expert at the HTTP protocol.

1.&nbsp; Start by opening the user profile you want to modify just like you were going to modify the user profile name.

2.&nbsp; Click on the particular HTTP transaction you want to modify.

3.&nbsp; Select a specific HTTP header and change the value as needed. 

![Modify][6]

4.&nbsp; Click **Save**.

Optionally you can also delete a particular HTTP transaction. ![Delete][1] next to the HTTP transaction you want to delete.

> You cannot restore an HTTP transaction you accidentally deleted.

![Delete Transaction][7]

## Find & Replace URL

Click ![Find][8] to find a portion of the URL for all steps and replace it with something else. This way you can easily run an existing Load Test against another server without recapturing or importing new traffic.

![Find and replace][9]

[1]: /img/features/testing-types/load-testing/modifying-tests/fig1.png
[2]: /img/features/testing-types/load-testing/modifying-tests/fig2.png
[3]: /img/features/testing-types/load-testing/modifying-tests/fig3.png
[4]: /img/features/testing-types/load-testing/modifying-tests/fig4.png
[5]: /img/features/testing-types/load-testing/modifying-tests/fig5.png
[6]: /img/features/testing-types/load-testing/modifying-tests/fig6.png
[7]: /img/features/testing-types/load-testing/modifying-tests/fig7.png
[8]: /img/features/testing-types/load-testing/modifying-tests/fig8.png
[9]: /img/features/testing-types/load-testing/modifying-tests/fig9.png
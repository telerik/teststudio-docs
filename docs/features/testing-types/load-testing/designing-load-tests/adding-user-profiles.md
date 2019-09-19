---
title: User Profiles in Load Testing
page_title: User Profiles in Test Studio Load Testing
description: "How to add user profiles in load test in Test Studio. User profiles in load testing represent what the HTTP traffic is for a particular user action or sequence Rename user profile name in Test Studio load test"
position: 1
---
# User Profiles in Test Studio Load Testing

User profiles represent what the HTTP traffic is for a particular user action or sequence. A new load test will have no user profiles. You must add at least one user profile. You may have as many user profiles contained in a load test as desired.

## Add a User Profile

Open a load test and select its __Design__ view.

![User Profile][1]

Continue by doing one of the following:

- <a href="#capturing-traffic">Capturing HTTP Traffic</a>
- <a href="#importing-traffic">Importing HTTP Traffic</a>

## Capturing Traffic

Before making a selection, close all browser instances as well as any other applications that may generate HTTP traffic, so that the user profile does not include extra HTTP traffic. Click the _'camera'_ button to open the Capture Traffic dialog.

![Capture Traffic][2]

This opens the **Capture Traffic** dialog where you can choose whether to capture traffic from a __Test Studio Web Test__ or __Capture new traffic session__.

### Capture From Existing Web Test

If you choose **Capture from existing web test**, a grid with all existing web tests in the project appears. Select the desired test to capture traffic from and choose the specific browser to execute the test against. Only traffic from this browser will be captured during the web test run. Once the web test execution finishes, the load test will display the <a href="/features/testing-types/load-testing/designing-load-tests/modifying-tests#user-profile-edit-mode" target="blank">captured traffic in edit mode</a>.

![Existing Web Test][3]

You can select a device to capture traffic from. Capturing from a remote source requires you to <a href="/features/testing-types/load-testing/configure-remote-device" target="blank">configure that device to use the remote proxy</a>.

### Capture New Web Session

If you choose __Capture new session__, you can select the browser to use. Then manually navigate to the desired page and perform the necessary browser session. Close the browser and click on the __Stop recording__ button to display the <a href="/features/testing-types/load-testing/designing-load-tests/modifying-tests#user-profile-edit-mode" target="blank">captured traffic in edit mode</a>. Click the **Save** button to confirm any changes in the User Profile captured traffic.

![Capture new session][4]

## Importing Traffic

Click the _'arrow'_ button to open the Import User Scenario dialog.

![Click Import traffic][5]

This opens the **Import User Scenario** dialog where you can choose whether to import traffic from a list with the existing  __User profiles__ or to __Browse an external file__.

### Import Existing User Profile

To import a user profile generated in another load test in the project, select the desired one in the list with available profiles by checking its checkbox and click __Add Selected__.

![Add existing user profile][6]

### Import HTTP Traffic from a Fiddler trace

Test Studio load tests also accept Fiddler files with captured web sessions. Choose the __Browse__ button to navigate to a location where the Fiddler trace files are stored. Then select the desired and click on the __Open__ button.

![Import Fiddler trace][7]

The <a href="https://docs.telerik.com/fiddler/Save-And-Load-Traffic/Tasks/CreateSAZ" target="blank">Fiddler trace file</a> is imported and added as a user profile in the load test. Think times are automatically added at the appropriate spots.

To explore the traffic in the imported user profiles, you can double click on each to <a href="/features/testing-types/load-testing/designing-load-tests/modifying-tests#user-profile-edit-mode" target="blank">show the imported traffic in edit mode</a>. Click the **Save** button to confirm any changes in the User Profile captured traffic.

## Remove User Profile

To remove an existing user profile click the _'X'_ button on the row of the user profile you want to delete.

> __Note:__ Once deleted that user profile is permanently removed - you cannot undo this deletion.

![Delete User Profile button][8]

## Change the User Profile Name

To change the name of a user profile you need to open the __Edit User Profile__ dialog.

1. Open the desired load test to modify.

1. To open the __Edit User Profile__ dialog click the _'pencil'_ icon on the row of the user profile you want to change. The same will be opened if you double click the same row.

    ![Edit User Profile button][9]

1. This will open the user profile in Edit mode and you can type in the new name at the top.

    ![Change User Profile Name][10]

1. Click the **Save** button to confirm the changes.


[1]: /img/features/testing-types/load-testing/adding-user-profiles/fig1.png
[2]: /img/features/testing-types/load-testing/capturing-traffic/fig2.png
[3]: /img/features/testing-types/load-testing/capturing-traffic/fig3.png
[4]: /img/features/testing-types/load-testing/capturing-traffic/fig4.png
[5]: /img/features/testing-types/load-testing/importing-traffic/fig5.png
[6]: /img/features/testing-types/load-testing/importing-traffic/fig6.png
[7]: /img/features/testing-types/load-testing/importing-traffic/fig7.png
[8]: /img/features/testing-types/load-testing/adding-user-profiles/fig8.png
[9]: /img/features/testing-types/load-testing/adding-user-profiles/fig9.png
[10]: /img/features/testing-types/load-testing/adding-user-profiles/fig10.png
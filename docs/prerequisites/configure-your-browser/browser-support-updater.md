---
title: Browser Support Update
page_title: Browser Support Update
description: "Test Studio supports instant updates for latest browser versions. Update Test Studio compatibility with latest browsers structure, dialogs, behavior, etc."
position: 1
---
# Browser Support Update

The __Browser support update__ allows Test Studio to stay compatible with the latest browser versions. Whenever a supported browser introduces any breaking changes in its functionalities, Test Studio needs to be updated.

When available, the __Browser support update__ notification appears next to the __Calibrate browsers__ button in the __Tests__ ribbon and indicates that you must update Test Studio.

![Browser support Update Notification][1]

1. Click the __Calibrate browsers__ button to access the __Project Settings__ > __Browsers__.

1. Click the __Update__ button next to the __New update available__ notification.

    ![Browser support Update Button][2]

2. Hitting the __Update__ button triggers the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Test Studio Services Cofigurator application</a> where you need to switch to its <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#browsers-tab" target="_blank">__Browsers__ tab</a>. 

    > __Note!__ 
    ><br> 
    > Running the Browser support update through the Test Studio Services Config Wizard requires admin rights. 

    ![Browser Update available](/img/features/scheduling-test-runs/create-scheduling-server/browsers-tab-update-aval.png)

After the update, restart Test Studio for the changes to take effect.

![Restart Required][3]

[1]: /img/features/dialogs-and-popups/dialog-handler-updater/fig1.png
[2]: /img/features/dialogs-and-popups/dialog-handler-updater/fig2.png
[3]: /img/features/dialogs-and-popups/dialog-handler-updater/fig3.png
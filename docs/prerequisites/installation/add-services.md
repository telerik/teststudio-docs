---
title: Add Test Studio Services
page_title: Add Scheduling, Storage Services and Executive Dashboard
description: "Test Studio Add Scheduling / Storage Services / Executive Dashboard after initial installation. I want to add scheduling to my current Test studio. How to schedule test lists on remote machines with Test Studio? Executive Dashboard is not available. How to add Executive Dashboard?"
previous_url: /user-guide/installation/trial-services.aspx, /user-guide/installation/trial-services
position: 6
---
# Add Test Studio Services after Initial Installation

After you have completed the Test Studio default installation, you can add the Test Studio Services and use the <a href="/features/scheduling-test-runs/remote-scheduled-run" target="_blank">Scheduling configuration provided by Test Studio</a>.

To add the Scheduling and Storage services and enable the machine to act as a Scheduling server, you will need to modify the existing Test Studio installation you have. You can refer to the steps described below how to change it.

Open the __Windows Control Panel__ and  navigate to its __Programs and Features.__ Find the Test Studio installation - it is called __Progress Telerik Test Studio 20XX.X.__ Right click on it and select the __Change__ option. 

![Programs and Features](/img/general-information/installation/add-services/fig1.png)

Click the __'Next'__ button in the Progress Telerik Test Studio 20XX.X Setup Wizard and choose the option to __Change__ the current installation.

![Change button](/img/general-information/installation/add-services/fig2.png)

Enable the services to install - usually the Scheduling, Storage and Executive Dashboard.

![Select services](/img/general-information/installation/add-services/fig3.png)

Proceed with the standard <a href="/prerequisites/installation/install-procedure" target="_blank">installation process.</a>

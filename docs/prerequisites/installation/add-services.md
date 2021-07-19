---
title: Modify Test Studio Installation
page_title: Modify Test Studio Installation
description: "Test Studio Add Scheduling / Storage Services / Executive Dashboard after initial installation. I want to add scheduling to my current Test studio. How to schedule test lists on remote machines with Test Studio? Executive Dashboard is not available. How to add Executive Dashboard?"
previous_url: /user-guide/installation/trial-services.aspx, /user-guide/installation/trial-services
position: 4
---
# Modify the Test Studio Installation

The completed Test Studio installation can be modified or repaired if necessary. By changing the installation, you can add or remove some of the Test Studio components such as Test Studio Services, Visual Studio plugin, etc.

## Trigger a Change of the Installation

Open the __Windows Control Panel__ and  navigate to its __Programs and Features.__ Find the Test Studio installation - it is called __Progress Telerik Test Studio 20XX.X.__ Right click on it and select the __Change__ option.

![Programs and Features](/img/general-information/installation/add-services/fig1.png)

> __Important__
> <br>
> <br>
> Test Studio installation must be re-configured from a Windows Administrator account.

Click the __'Next'__ button in the Progress Telerik Test Studio 20XX.X Setup Wizard and choose the option to __Change__ the current installation.

![Change button](/img/general-information/installation/add-services/fig2.png)

In the next screen of the Installation Wizard select/deselect the desired components.

## Add Test Studio Services after Initial Install

After you have completed the Test Studio default installation, you can add the Test Studio Services and use the <a href="/features/scheduling-test-runs/remote-scheduled-run" target="_blank">Scheduling configuration provided by Test Studio</a>.

Once the Installation Wizard is opened in Change mode, enable the services to install - usually the Scheduling, Storage and Executive Dashboard.

![Select services](/img/general-information/installation/add-services/fig3.png)

Proceed with the standard <a href="/prerequisites/installation/install-procedure" target="_blank">installation process.</a>

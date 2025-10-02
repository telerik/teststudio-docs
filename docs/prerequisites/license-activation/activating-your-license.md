---
title: Activating Your License
page_title: Activating Your License
description: "Test Studio activate license. Test Studio trial license. Login to your Telerik account "
position: 1
---
# Activate Your Test Studio License

<a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> uses a per machine license and it can be activated from a licensed Telerik user. All users, both trial and purchased, need to perform the license activation before using the tool.

You can find the following topics in the article: 

- [Activate Your Test Studio License](#activate-your-test-studio-license)
  - [Launch Test Studio and Login](#launch-test-studio-and-login)
    - [Direct Login](#direct-login)
    - [SSO Login](#sso-login)
  - [Choose Test Studio Edition](#choose-test-studio-edition)
  - [Choose Test Studio License](#choose-test-studio-license)
  - [Possible Troubles](#possible-troubles)
    - [0 Seats Available](#0-seats-available)
    - [Connection Error](#connection-error)

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

## Launch Test Studio and Login

Start Test Studio product to launch the __Activation Wizard__ asking for login credentials. You need to login with the email address and password for the <a href="https://www.telerik.com/account/" target="_blank">Telerik.com</a> account, which has the Test Studio license assigned. You can choose the activation method by direct login, login through a browser or <a href="/prerequisites/license-activation/manual-activation" target="_blank">activate manually</a>, which is applicable for activating Test Studio on machines without access to the internet. 

![Activation Login screen](/img/prerequisites/license-activation/activating/fig1.png)

### Direct Login

You can enter the Telerik account credentials directly in the activation wizard and use the __Login__ button to login. 

![Login button](/img/prerequisites/license-activation/activating/fig2.png)

### SSO Login

Choose the __SSO Login__ button to authenticate in a browser.

![SSO Login button](/img/prerequisites/license-activation/activating/fig3.png)

The default set browser opens up and redirects you to the Telerik account login page - follow the on-screen instructions to enter your Telerik username and password and login. 

![Browser Login](/img/prerequisites/license-activation/activating/fig4.png)

If you are already logged in to the Telerik.com page in the same browser, the authentication gets checked and you can proceed with choosing the version to activate.

## Choose Test Studio Edition

After successful login the __Activation Wizard__ lets you choose the version of Test Studio, which you want to activate on the machine. On this screen you can see the logged Telerik user and all licenses assigned to it. 
If the user has a single type of Test Studio license, there is a single listing for it. Select the license to activate and hit the __Activate Selected Version__ button to proceed.

![Choose Test Studio version](/img/prerequisites/license-activation/activating/fig6.png)

## Choose Test Studio License

The following screen appears if the logged user has more than one purchase orders or more than one license in the order - all orders are listed as separate items with their amount of available seats.  

> __Tip__
> 
> The __'Available Seats'__ number is the amount of the not activated licenses. Test Studio licenses are associated with the specific machine, so once a license is activated there is a seat used. Check [here](#0-seats-available) if you get '0 available seats'. 

Choose a license with available seats and click the __Activate Selected License__ button. Once the license is activated for this machine, the __Test Studio Welcome Screen__ pops up and let's you <a href="/getting-started/first-project#starting-welcome-screen" target="_blank">start your journey</a>. 

![Choose Test Studio license](/img/prerequisites/license-activation/activating/fig7.png)

## Possible Troubles

On specific occasions the activation process may not complete successfully. The most common issues you may encounter are listed below.

### 0 Seats Available

When trying to activate a Test Studio license, you may see that there are no seats available, although you have a purchased license. This can happen if the machine on which a Test Studio license was activated:

- has been recently re-imaged
- has been recently replaced
- is not accessible anymore for whatever reason

If the license was not deactivated while the machine was still active, you will notice that a seat from the purchased license is occupied for that computer.

To be able to use that license seat again, you need to deactivate this license manually from your Telerik account - visit the <a href="/getting-started/installation/re-activating-your-license" target="_blank">Manual License Deactivation</a> article for a step-by-step guide.

### Connection Error

If you perform the activation process as described, but get an error related to the connection, you can try to activate the Test Studio license manually. You can proceed to the __Activate Manually__ button and follow the steps in the <a href="manual-activation" target="_blank">Manual Activation</a> help article.



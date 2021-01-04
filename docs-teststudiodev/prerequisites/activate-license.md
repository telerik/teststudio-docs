---
title: Activate License
page_title: Activate License | Test Studio Dev Documentation
description: How to activate Test Studio Dev license
slug: prerequisites/activate-license
tags: isntallation
published: True
position: 2
---
# Activate Test Studio Dev License

After installing Test Studio Dev, you will be asked to activate your license. During this process, your machine creates its own unique key and provides it to our server. We use this key to generate a unique license key for the installation of the product.

> All users, both trial and purchased, will need to activate their product after installation before they can begin using the tool.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

<br>
Start your Visual Studio and you will be prompted to login to activate the installation. Input the email address and password that correspond to your <a href="https://www.telerik.com/account" target="_blank">Telerik.com account</a>.

![Login to activate](images/installation/activate-ts-dev.png)

Select the Test Studio Dev license and click __'Activate Selected License'__. 

![Activate Licence](images/installation/choose-license.png)

## Manual Activation

The following steps demonstrate how to manually activate Test Studio on a machine without an internet connection. Please note that while the machine that will run Test Studio is not connected to the internet, you will need access to the internet and our website to complete this process.

1.Select __Activate Manually__.

![Activate Manually](images/installation/manual-activation.png)

2.Copy your machine key from the __Machine Info Key__ field for later use.

![Machine Key](images/installation/fig3.png)

3.Navigate to the <a href="https://www.telerik.com/account/your-products/testing-tools-manage-license-keys" target="_blank">License Keys Management Form</a> and click the _Add a key_ button.

![License Keys Management Form](images/installation/fig4.png)

4.Select Product from the drop down menu. Input your machine info key within the provided field, the machine name and friendly name, then click the Generate Key button. 

![Select Product](images/installation/fig5.png)

> There are reserved words that cannot be used for Machine key, Machine name and Friendley name. The words are **telerik**, **admin**, **administrator**, **sitefinity**, **icenium**, **kendo**, **kendoui** and **moderator**. 

5.A confirmation appears that the Key was successfully created. Locate the key and click __View key__.

![Copy key](images/installation/view-key.png)

6.Select and copy the registration key. Then paste it within the respective field in Test Studio Dev Activation wizard, then click __Activate__.

![Activate](images/installation/fig7.png)

>If your machine was freshly imaged or replaced and you need to re-activate your license (0 seats available) on the new machine, please visit <a href="/advanced-topics/installation/re-activating-your-license" target="_blank">Re-Activating your License</a> article.
---
title: Installation Prerequisites
page_title: Installation Prerequisites
description: "What machine to choose for installing Test Studio on. User permissions, Visual Studio requirements for installing Test Studio. "
position: 0
---
# Installation Prerequisites

Before you install Test Studio, make sure that the following requirements are met:

- The computer where you are going to install Test Studio meets the hardware and software requirements described in <a href="/system-requirements" target="_blank">System Requirements</a>.

- Your user account has administrator permissions to install, change, repair or uninstall Test Studio. You must be logged on as Administrator or belong to the Administrators group on the computer.

- If you plan on using the Test Studio plugin in Visual Studio 2017, <a href="#modify-visual-studio-2017-installation" target="_blank">add the __Testing Tools Core Features__ component in the Visual Studio installation</a>.

- If you plan on running Test Studio test automation on Windows Server OS and use IE, <a href="#configuring-windows-server-for-test-studio-test-automation" target="_blank">turn off the __Windows component Internet Explorer Enhanced Security Configuration__</a>.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

## Visual Studio 2022 Installation Specifics

Visual Studio 2022 requires minimum _Workload_ added in its installation to be compatible with the Test Studio plugin for Visual Studio.

Before installing Test Studio, you need to modify the Visual Studio 2022 installation and add the **.Net desktop development** workload's components. Once this is added, complete the Visual Studio 2022 standard installation process. Then perform the <a href="/prerequisites/installation/install-procedure" target="_blank">standard Test Studio installation</a>.

![Visual Studio 2022 Installation](/img/general-information/installation/vs2022/fig1.png)

## Modify the Visual Studio 2017 Installation

Visual Studio 2017 requires an additional feature in its installation to be compatible with the Test Studio plugin for Visual Studio.

Before installing Test Studio, you need to modify the Visual Studio 2017 installation and add the **Testing Tools Core Features** component under Debugging and Testing section. Once you enable this component, complete the Visual Studio 2017 standard installation process. Then perform the <a href="/prerequisites/installation/install-procedure" target="_blank">standard Test Studio installation</a>.

![Visual Studio 2017 Installation][1]

[1]: /img/general-information/installation/vs2017/vs2017installation.png

## Configuring Windows Server for Test Studio Test Automation

If you plan on running Telerik test automation on Windows Server machine and using IE, you will need to turn off the __Internet Explorer Enhanced Security Configuration__ Windows component. This component is a great feature and highly recommended for machines actually being used as production servers. However, it interferes with test automation running against the IE browser.

### Turn off Internet Explorer Enhanced Security Configuration on a Windows Server Machine

The below steps are applicable for Windows Server versions 2012, 2016, 2019.

1.	Open __Server Manager__.

	![Server Manager](/img/general-information/installation/configure-windows-server/fig4.png)

2. In the left pane, select __Local Server__.

	![Local Server](/img/general-information/installation/configure-windows-server/fig5.png)

3. In the right pane under __Properties__, disable IE Enhanced Security Configuration.

	![Properties](/img/general-information/installation/configure-windows-server/fig6.png)


### Turn off Internet Explorer Enhanced Security Configuration on Windows Server 2008

1. Click __Start > Administrative Tools > Server Manager__.
2. In the __Security Information__ section find and click on __Configure IE ESC__ (in the box on the right)

	![Configure IE ESC](/img/general-information/installation/configure-windows-server/fig2.png)

3. Turn off __IE ESC__ for both __Administrators__ and __Users__.

	![Turn off IE ES](/img/general-information/installation/configure-windows-server/fig3.png)

4. Click __OK__.
5. Close __Server Manager__.

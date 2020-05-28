---
title: Configure Windows Server
page_title: Configuring Windows Server 2008/2012 for Test Automation
description: "Test Studio Configuring Windows Server 2008/2012 for Test Automation"
position: 9
publish: false
---
# Configuring Windows Server 2008/2012 for Test Automation #


If you plan on running Telerik test automation on either Windows Server 2008 or 2012 and use IE, you will need to turn off the Windows component __Internet Explorer Enhanced Security Configuration__. This component is a great feature and highly recommended for machines actually being used as production servers. However, it interferes with test automation running against the IE browser.

## Turn off Internet Explorer Enhanced Security Configuration on Windows Server 2012 ##

1.	Open __Server Manager__.

	![Server Manager](/img/general-information/installation/configure-windows-server/fig4.png)

2. In the left pane, select the __Local Server__.

	![Local Server](/img/general-information/installation/configure-windows-server/fig5.png)

3. In the right pane under __Properties__, disable IE Enhanced Security Configuration.

	![Properties](/img/general-information/installation/configure-windows-server/fig6.png)


## Turn off Internet Explorer Enhanced Security Configuration on Windows Server 2008 ##

1. Click __Start > Administrative Tools > Server Manager__.
2. In the __Security Information__ section find and click on __Configure IE ESC__ (in the box on the right)

	![Configure IE ESC](/img/general-information/installation/configure-windows-server/fig2.png)

3. Turn off __IE ESC__ for both __Administrators__ and __Users__.

	![Turn off IE ES](/img/general-information/installation/configure-windows-server/fig3.png)

4. Click __OK__.
5. Close __Server Manager__.


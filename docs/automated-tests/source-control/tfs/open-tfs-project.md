---
title: Open TFS-Controlled Project
page_title: Open TFS-Controlled Project
description: "Open a Test Studio Project from TFS"
previous_url: /features/source-control/open-tfs-project
position: 2
---
# Open TFS-Controlled Project

<a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> provides built-in integration with TFS source control.

The below steps guide you how to open a project, which is stored in the TFS server and create a local copy of it on your hard drive.

1. Launch Test Studio and click the **Open** button in the **Source Control** ribbon.

![Connect](/img/features/source-control/open-tfs-project/fig1.png)

2. The **Bind to Source Control** dialog appears. Fill in the appropriate information and click **Connect**.

![Connect to TFS](/img/features/source-control/open-tfs-project/fig2.png)

3. Pick the destination directory in TFS and click **OK**.

4. You can now select a test and click ![Check-in](/img/features/source-control/open-tfs-project/fig3.png) and ![Check Out](/img/features/source-control/open-tfs-project/fig4.png) buttons in the **Source Control** ribbon.

![Checkin Checkout](/img/features/source-control/open-tfs-project/fig5.png)

The project view displays the source control status of individual tests.

![Individual Tests](/img/features/source-control/open-tfs-project/fig6.png)


- ![Plus](/img/features/source-control/open-tfs-project/fig7.png) appears next to newly created items (part of a source controlled project) that are not added to the source control yet.
- ![Lock](/img/features/source-control/open-tfs-project/fig8.png)appears next to checked in tests.
- ![Check](/img/features/source-control/open-tfs-project/fig9.png)appears next to checked out tests.
- ![Remotely](/img/features/source-control/open-tfs-project/fig10.png)appears next to tests which are in conflict.
     
> In general, Test Studio does not check out a project from source control when the project opens. However, if one or more project files are out of date (for example, they were created by an older version of Test Studio), Test Studio will attempt to check them out for an update. This will continue until an up-to-date version of the files are checked into source control.


---
title: Open TFS-Controlled Project
page_title: Open TFS-Controlled Project
description: "Open a Test Studio Project from TFS"
previous_url: /features/source-control/open-tfs-project
position: 2
---
# Open TFS-Controlled Project

1.&nbsp; Launch Test Studio and click the **Open** button in the **Source Control** ribbon.

![Connect][1]

2.&nbsp; The **Bind to Source Control** dialog appears. Fill in the appropriate information and click **Connect**.

![Connect to TFS][2]

3.&nbsp; Pick the destination directory in TFS and click **OK**.

4.&nbsp; You can now select a test and click ![Check-in][3] and ![Check Out][4] buttons in the **Source Control** ribbon.

![Checkin Checkout][5]

The project view displays the source control status of individual tests.

![Individual Tests][6]


- ![Plus][7] appears next to newly created items (part of a source controlled project) that are not added to the source control yet.
- ![Lock][8]appears next to checked in tests.
- ![Check][9]appears next to checked out tests.
- ![Remotely][10]appears next to tests which are in conflict.
     
> In general, Test Studio does not check out a project from source control when the project opens. However, if one or more project files are out of date (for example, they were created by an older version of Test Studio), Test Studio will attempt to check them out for an update. This will continue until an up-to-date version of the files are checked into source control.

[1]: /img/features/source-control/open-tfs-project/fig1.png
[2]: /img/features/source-control/open-tfs-project/fig2.png
[3]: /img/features/source-control/open-tfs-project/fig3.png
[4]: /img/features/source-control/open-tfs-project/fig4.png
[5]: /img/features/source-control/open-tfs-project/fig5.png
[6]: /img/features/source-control/open-tfs-project/fig6.png
[7]: /img/features/source-control/open-tfs-project/fig7.png
[8]: /img/features/source-control/open-tfs-project/fig8.png
[9]: /img/features/source-control/open-tfs-project/fig9.png
[10]: /img/features/source-control/open-tfs-project/fig10.png


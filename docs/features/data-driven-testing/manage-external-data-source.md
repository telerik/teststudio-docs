---
title: Manage External Data Source
page_title: Manage External Data Source
description: "Manage Test Studio external data sources. How to update the data source added in Test Studio project. "

position: 6
---
# Manage External Data Source

When a <a href="/features/data-driven-testing/add-data-source" target="_blank">data source is added in a Test Studio project</a>, it is actually copied to the **_ProjectRootFolder_\Data** sub-folder. This is the location, from where the file is accessed in test run-time, and any required changes in the data source must be applied to the file in this location. 

In order to modify any external data file, you can directly open it from the mentioned folder, or you can easily access it through Test Studio.

> __Tip__
><br>
><br>
> The project's root folder can be accessed through the <a href="/features/project-explorer/overview#project-context-menu-options" target="_blank">Project Explorer Context menu</a> using the option _Open Folder in Windows Explorer_.

## Access the Referenced External Data Sources

Click the **Manage** button from the _Data Source_ section in the _Project_ ribbon to open the _Manage Data Source_ dialog.

![Manage Button][1]

## Choose an External File to Edit

If there are more than one data source file added to the project, there will be a list of all these files. Choose the one you need to modify and click the **Edit** icon to edit that data source.

![Edit Data Source][2]

## Delete an External File

If you need to remove a data source from a Test Studio project, you need to remove its reference as well.

> __Note__
><br>
><br>
> Before you delete an external data source from the project, ensure to <a href="/features/data-driven-testing/bind-test-data-source#remove-data-binding" target="_blank">remove its binding to any of the tests</a>.

Then, you can open the _Manage Data Source_ dialog, choose the data file to delete and click the **Delete** button next to it.

![Delete Data Source][3]

[1]: /img/features/data-driven-testing/manage-external-data-source/fig1.png
[2]: /img/features/data-driven-testing/manage-external-data-source/fig2.png
[3]: /img/features/data-driven-testing/manage-external-data-source/fig3.png
[4]: /img/features/data-driven-testing/manage-external-data-source/fig4.png

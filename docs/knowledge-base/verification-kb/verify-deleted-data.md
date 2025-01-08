---
title: Verify Deleted Data
page_title: Verify Deleted Data
description: verify that an element does not exist within a Test Studio test
position: 1
---
# Verify Deleted Data

I would like to verify that an element does not exist, like after deleting a row from a data grid.

## Solution

This is possible with a Wait for ExistsNot verification. Here's an example against <a href="http://demos.telerik.com/aspnet-ajax/grid/examples/columns-rows/rows/drag-and-drop/defaultcs.aspx" target="_blank">this Telerik demo site</a>:

1.&nbsp; Drag the first DataGridItem from **Pending Orders** to **Shipped Orders**.

![Drag the row][1]

2.&nbsp; Before deleting the DataGridItem, create the **Wait for ExistsNot** verification while it still exists.

![Wait for exists not][2]

3.&nbsp; Drag the *DataGridItem* from **Shipped Orders** to the **Recycle Bin**.

![Remove the datagriditem][3]

4.&nbsp; Click **OK** on the Confirm dialog.

5.&nbsp; Move the **Wait for ExistsNot** step to the last position.

![Remove the datagriditem][4]

6.&nbsp; Execute the test.

[1]: /img/knowledge-base/verification-kb/verify-deleted-data/fig1.png
[2]: /img/knowledge-base/verification-kb/verify-deleted-data/fig2.png
[3]: /img/knowledge-base/verification-kb/verify-deleted-data/fig3.png
[4]: /img/knowledge-base/verification-kb/verify-deleted-data/fig4.png
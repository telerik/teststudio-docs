---
title: Verify Deleted Data
page_title: Verify Deleted Data
description: verify that an element does not exist within a Test Studio test
position: 1
---
## Verify Deleted Data

I would like to verify that an element does not exist, like after deleting a row from a data grid.

## Solution

This is possible with a Wait for ExistsNot verification. Here's an example against <a href="http://demos.telerik.com/aspnet-ajax/grid/examples/columns-rows/rows/drag-and-drop/defaultcs.aspx" target="_blank">this Telerik demo site</a>:

1. Drag the first DataGridItem from **Pending Orders** to **Shipped Orders**.

![Drag the row](/img/knowledge-base/verification-kb/verify-deleted-data/fig1.png)

2. Before deleting the DataGridItem, create the **Wait for ExistsNot** verification while it still exists.

![Wait for exists not](/img/knowledge-base/verification-kb/verify-deleted-data/fig2.png)

3. Drag the *DataGridItem* from **Shipped Orders** to the **Recycle Bin**.

![Remove the datagriditem](/img/knowledge-base/verification-kb/verify-deleted-data/fig3.png)

4. Click **OK** on the Confirm dialog.

5. Move the **Wait for ExistsNot** step to the last position.

![Remove the datagriditem](/img/knowledge-base/verification-kb/verify-deleted-data/fig4.png)

6. Execute the test.


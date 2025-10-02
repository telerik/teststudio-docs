---
title: Merge Page Nodes
page_title: Merge Page Nodes
description: Merge Page Nodes in Test Studio elements repository. Each time I start a recording session I get a new element recorded for the same control under different page node in the elements explorer. The element uses the same find expression, but the page URL differs as it has dynamically generated part. How can I reuse the same recorded element
position: 7
---
#Merge Page Nodes#

* <a href="/knowledge-base/project-configuration-kb/merge-page-nodes#page-nodes">Page nodes</a>
* <a href="/knowledge-base/project-configuration-kb/merge-page-nodes#frames">Frame nodes</a>


##Page Nodes##

The default for the **Compare Mode** in <a href="/features/project-settings/recording-options" target="_blank">Project Settings > Recording</a> is *FullPathAndQuery*. Depending on your application, this can cause duplication in the Elements Explorer. Although the page node is not used to locate an element during execution, it's best to consolidate duplicate page nodes for organizational and maintenance purposes. For example:

1. Navigate to http://www.bing.com/?123

2. Enter text into the query box.

3. Click the Search button.

4. Notice the Elements Explorer.

	![Element explorer with one page node][1]

5. Navigate to http://www.bing.com/?456

6. Repeat steps 2 and 3.

7. Notice the Elements Explorer.

8. The *SbFormQText* and *SbFormGoSubmit* elements are duplicated under each page node. This should not cause an Unable to locate element failure during execution, however it can make for unnecessary maintenance and disorganization in your project.

	![Element explorer with two page node][2]

9. To prevent duplication moving forward, change the **Compare Mode** to *FullPath*.

	![Compare mode][3]

10. To merge the **existing duplicates**, highlight each page and change its **CompareMode** property to FullPath.

	![Change compare mode][4]

	![Select node][5]

11. Elements explorer refreshes automatically and the nodes merge, the tree structure is better organized, and any maintenance needed on an element can now be done in one place.

	![Nodes merge][6]


If *FullPath* is not applicable to your project, review the <a href="/features/project-settings/recording-options" target="_blank">Project Settings > Recording Options</a> page and select the Compare Mode that best suits your needs.

##Frames##

An element directly under a page node is located entirely by its Find Settings. Conversely, an element within a frame must be located via the frame first.

1. Here we see a similar situation due to dynamic frame IDs.

	![Two frame nodes][7]

2. To merge duplicate frame nodes caused by dynamic frame IDs, strip the dynamic portion from each ID and use a tilde (~) to indicate a partial match. See <a href="/getting-started/test-recording/Frames" target="_blank">this page</a> for more information on frames.

	![New ID][8]

3. Click **Refresh** to merge the duplicates.

	![Merge nodes][9]


[1]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig1.png
[2]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig2.png
[3]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig3.png
[4]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig4.png
[5]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig5.png
[6]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig6.png
[7]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig7.png
[8]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig8.png
[9]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig9.png
[10]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig10.png
[11]: /img/knowledge-base/project-configuration-kb/merge-page-nodes/fig11.png

---
title: Dynamic IDs
page_title: Dynamic IDs
description: Web site or application generates ID attributes for its elements dynamically. This causes the Test Studio tests to fail because once the ID attribute for a given element changes, it can no longer be identified. How to choose find logic for elements with dynamic ids. 
previous_url: /user-guide/knowledge-base/test-automation/dynamically-generated-id-attributes.aspx
position: 1
---
## Working Around Dynamically Generated ID Attributes

*Your web site or application generates ID attributes for its elements dynamically. This causes your tests to fail because once the ID attribute for a given element changes, it can no longer be identified.*

We recommend that you consider changing your application in order to make it use non-dynamically generated IDs. It will pay off in time saved on automation tasks. However, we realize this will not be an option for everyone. In this case you need to bypass the ID attributes. There are two ways to do this:

## Edit the Find Logic Configuration for the Project

1. Open the Project Settings menu:

	<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
	<td>
	
    ![Standalone][1]<br>**Standalone version**</td>
	<td>
	
	![VS Plugin][2]<br>**VS Plugin**</td>
	<tr>
	</table>

2. Go to **Find Logic** from the navigation bar on the left:

	![Identificaiton logic][3]

This is a list of the attributes Test Studio will use to build the Find Logic for elements when you're recording a test. The attributes are listed in order of priority.

**Note:** Keep in mind that the Find Expression for a given element will only use two attributes.

You can delete the ID tag from the list altogether or you can can move it further down to decrease its priority. After you've saved the changes, any new tests you record will use the new configuration designed to avoid ID tags.

## Manually Edit the Find Expression for the Affected Elements

A recorder step is failing due to a changed ID. If you click on the recorder step from the Steps menu, an Element in the Elements Explorer becomes highlighted in the Elements Explorer:

![Element explorer][4]

The highlighted element is the one used in the step. Right-click on it and choose "Edit Element". This will bring up the Find Expression Builder. From here you can edit your Find Expression in order to make it better-suited to your specific automation task. See our article on how to <a href="/features/elements-explorer/find-element" target="_blank">Change How an Element is Found</a>.
 
The specific solution will depend on your application. In some cases, only parts of the ID will change (e.g. only the prefix or suffix will be different). In this case you can change the condition from "**Exact**" to "**Contains**" and exclude all the non-constant parts of the ID from the Find Expression. Ensure the Find Expression is still unique.

[1]: /img/knowledge-base/test-automation-kb/dynamic-ids/fig1.png
[2]: /img/knowledge-base/test-automation-kb/dynamic-ids/fig2.png
[3]: /img/knowledge-base/test-automation-kb/dynamic-ids/fig3.png
[4]: /img/knowledge-base/test-automation-kb/dynamic-ids/fig4.png
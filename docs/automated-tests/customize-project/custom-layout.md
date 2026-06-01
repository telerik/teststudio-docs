---
title: Customize Test Studio Layout
page_title: Customize Test Studio Layout
description: "Customize Test Studio Layout. Where is the Properties/ Step Builder/ Elements explorer/ Project Explorer panel in Test Studio. Switch to Dark theme in Test Studio. Switch to light theme in Test Studio"
position: 1
---
# Customize Test Studio's Layout

Test Studio layout can be customized to fit your needs and personal preferences. 

In this article you can find info on how to: 

- [Switch between the predefined layouts](#predefined-layouts)
- [Manually adjust the layout](#arrange-test-studio-layout-manually)
- [Save custom layout](#save-a-customized-layout)
- [Switch between Light and Dark theme](#switch-between-light-and-dark-theme)

When you first start Test Studio its default layout is the __Compact__ one using the __Light__ theme.

![Default Compact layout and light theme](/img/automated-tests/customize-project/custom-layout/fig1.png)

## Predefined Layouts

The preset layouts rearrange the panes in the Test Studio project to focus your attention on certain tools. The three predefined layouts are listed below and you can find additional notes on each of them:

* [Compact (default)](#compact-layout)

* [High Productivity](#high-productivity-layout)

* [Advanced](#advanced-layout)

![Layout dropdown and list of predefined layouts](/img/automated-tests/customize-project/custom-layout/fig2.png)

### Compact Layout

In the __Compact__ layout you have the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a>, the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a> and the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>  <a href="#dock-or-undock-a-panel">docked</a> and visible. The <a href="/features/custom-steps/overview" target="_blank">Step Builder</a>, the Properties pane and <a href="/features/coded-steps/output-panel" target="_blank">Output Panel</a> are <a href="#hide-or-show-a-panel">hidden and pinned</a> on the right side of the project area.

![Compact layout](/img/automated-tests/customize-project/custom-layout/fig2a.png)

### High Productivity Layout

In the __High Productivity__ layout you have all panels <a href="#dock-or-undock-a-panel">docked</a> and visible in the project area - the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a>, the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a>, the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>, the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a>, the __Properties__ pane and <a href="/features/coded-steps/output-panel" target="_blank">__Output Panel__</a>.

![High Productivity layout](/img/automated-tests/customize-project/custom-layout/fig2b.png)

### Advanced Layout

In the __Advanced__ layout you get the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a>, the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a> and the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>  <a href="#dock-or-undock-a-panel">docked</a> and visible. The <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a>, the __Properties__ pane and <a href="/features/coded-steps/output-panel" target="_blank">__Output Panel__</a> are also docked and visible in the project area, but tabbed to switch between these.

![Advanced layout](/img/automated-tests/customize-project/custom-layout/fig2c.png)

## Arrange Test Studio Layout Manually

Test Studio allows you to move all its <a href="/getting-started/first-project#test-studio-project-layout" target="_blank">panels in the project</a> to another place in the working area, or pin these on the side to hide them. Below are the possible actions described: 

- [Dock/Undock Panes](#dock-or-undock-a-panel)
- [Hide/Show Panes](#hide-or-show-a-panel)

### Dock or Undock a Panel

Use the __Dock/Undock__ button in the upper right corner of each panel to change its position in the project layout.

![undock](/img/automated-tests/customize-project/custom-layout/fig3.png)

> __Tip__
><br>
><br>
> <a href="https://www.telerik.com/videos/teststudio/that-s-neat!-dockable-windows-in-test-studio">Check this video</a> to see how panels in Test Studio can be undocked and docked back.

The __Undock__ detaches the pane from its original position and displays it as a separate window. Click on the title bar of the pane and __use the mouse to drag and drop it__ anywhere in the project area. Circle with directions - top, bottom, left, right and center - is displayed to help you choose the preferred position relative to the target panel.

![choose panel position](/img/automated-tests/customize-project/custom-layout/fig4.png)

If you want to place the panel separately, you can use the arrows on the right, left, top and bottom sides of the Test Studio project window.

![choose window position](/img/automated-tests/customize-project/custom-layout/fig4a.png)

If you select the center of the target panel, the undocked panel will appear as a tab next to the target panel.

<table id="no-table" style="border:none;">
	<tr style="background-color: transparent; border:none;">
		<td>

<img src="/img/automated-tests/customize-project/custom-layout/fig5.png" alt="choose center" /></td>
<td>

<img src="/img/automated-tests/customize-project/custom-layout/fig6.png" alt="tabs" /></td>
</tr>
</table>

### Hide or Show a Panel

Use the __Pin/Unpin__ button in the upper right corner of each panel to show or hide it in the project area.

![Pin or Unpin buttons](/img/automated-tests/customize-project/custom-layout/fig8a.png)

The __Unpin__ button hides the pane from the project area and adds it as tab on the left or right side of Test Studio window. Hover over the side tab to show the panel.

![unpin and show pane](/img/automated-tests/customize-project/custom-layout/unpin-pane.gif)

The __Pin__ button pins the pane onto the project working area and keeps it always visible.

![pin a pane](/img/automated-tests/customize-project/custom-layout/show-and-pin-pane.gif)

## Save a Customized Layout

Once you apply any change in the panels position or size, the currently selected layout is switched to __Current__. This is the layout, which is used on the next start of Test Studio.

![Current layout](/img/automated-tests/customize-project/custom-layout/fig9.png)

You can save these current changes in the layout into a user defined layout. That way you can switch to this at any time. Choose the __Save As__ option from the _Layouts_ dropdown.

![Save current into user defined layout](/img/automated-tests/customize-project/custom-layout/fig10.png)

You have two options in the __Save As__ dialog - to save the layout as a new user defined one, or to overwrite an existing one.

![Save current into new user defined layout](/img/automated-tests/customize-project/custom-layout/fig11.png)

If you choose to overwrite an existing user defined layout, a list with all already saved layouts appears to select the one to overwrite.

![Overwrite existing user defined layout](/img/automated-tests/customize-project/custom-layout/fig12.png)

The user defined layouts can be renamed, or deleted.

![Rename or Delete existing user defined layout](/img/automated-tests/customize-project/custom-layout/fig13.png)

> __Tip__
><br>
><br>
> To __reset the default project view__ you can switch to any of the predefined layouts. 

## Switch between Light and Dark Theme

Test Studio comes with a __Light__ and __Dark__ theme. Choose the one that suits your needs best and <a href="/features/project-settings/theme" target="_blank">apply it through the Project Settings</a>.

![Dark theme](/img/features/project-settings/theme/fig6.png)

> __Note__
><br>
><br>
> Switching between the themes __requires restart of Test Studio__ to apply.

## See Also

- <a href="https://www.telerik.com/videos/teststudio/that-s-neat!-dockable-windows-in-test-studio">That’s neat! Dockable windows in Test Studio</q>



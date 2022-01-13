---
title: Customize Test Studio Layout
page_title: Customize Test Studio Layout
description: "Customize Test Studio Layout. Where is the Properties/ Step Builder/ Elements explorer/ Project Explorer panel in Test Studio. Switch to Dark theme in Test Studio. Switch to light theme in Test Studio"
position: 1
---
# Customize Test Studio's Layout

Test Studio layout can be customized to fit your needs and personal preferences. You can reorder all panels manually or choose from the predefined layouts. You can switch between _Light_ and _Dark_ themes.

The default layout when you start Test Studio is the __Compact__ layout in the __Light__ theme.

![default layout][1]

## Predefined Layouts

The preset layouts rearrange the panes in the Test Studio project to focus your attention on certain tools. The three predefined layouts are

* Compact (default)

* High Productivity

* Advanced

![preset layouts][2]

### Compact Layout

In the __Compact__ layout you can see <a href="#dock-or-undock-a-panel">docked</a> and visible the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a>, the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a> and the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>. The <a href="/features/custom-steps/overview" target="_blank">Step Builder</a>, the Properties pane and <a href="/features/coded-steps/output-panel" target="_blank">Output Panel</a> are <a href="#hide-or-show-a-panel">hidden and pinned</a> on the right side of the project area.

![Compact layout][2a]

### High Productivity Layout

In the __High Productivity__ layout you can see all panels <a href="#dock-or-undock-a-panel">docked</a> and visible in the project area - the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a>, the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a>, the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>, the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a>, the __Properties__ pane and <a href="/features/coded-steps/output-panel" target="_blank">__Output Panel__</a>.

![High Productivity layout][2b]

### Advanced Layout

In the __Advanced__ layout you can see <a href="#dock-or-undock-a-panel">docked</a> and visible the <a href="/features/elements-explorer/overview" target="_blank">__Elements Explorer__</a>, the <a href="/features/project-explorer/overview" target="_blank">__Project Explorer__</a> and the <a href="/features/test-maintenance/steps-pane" target="_blank">__Edit Project Items Pane__</a>. The <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a>, the __Properties__ pane and <a href="/features/coded-steps/output-panel" target="_blank">__Output Panel__</a> are docked and tabbed to switch between these.

![Advanced layout][2c]

## Switch between Light and Dark Theme

Test Studio comes with a _Light_ and _Dark_ theme. Choose the one that suits your needs better and <a href="/features/project-settings/theme" target="_blank">apply it through the Project Settings</a>.

![Dark theme](/img/features/project-settings/theme/fig6.png)

> __Note__
><br>
><br>
> You need to restart Test Studio to apply the changed theme.

## Manual Layout Adjustment

You can move the <a href="/getting-started/first-project#test-studio-project-layout" target="_blank">panels in a Test Studio project</a> to another area, or pin these on the side to hide them.

### Dock or Undock a Panel

Use the _Dock/Undock_ buttons in the upper right corner of each panel to change its position in the project layout.

> __Tip__
><br>
><br>
> <a href="https://www.telerik.com/videos/teststudio/that-s-neat!-dockable-windows-in-test-studio">Check this video</a> to see how panels in Test Studio can be undocked and docked back.

![undock][3]

The _Undock_ detaches the pane from its original position and displays it as a separate window. You can use the mouse tp drag and drop this window anywhere in the project area. To help you choose the preferred position relative to the target panel, there is a circle with directions - top, bottom, left, right and center.

![choose panel position][4]

If you want to place the panel separately, you can use the arrows on the right, left, top and bottom sides of the Test Studio project window.

![choose window position][4a]

If you select the center of the target panel, the undocked panel will appear as a tab next to the target panel.

<table id=no-table>
	<tr>
		<td>![choose center][5]</td>
		<td>![tabs][6]</td>
	</tr>
<table>

### Hide or Show a Panel

To hide a panel from the project's working area, select the _Pin_ button in its upper right corner. This pins the panel on the left or right side of Test Studio window and auto-hides it. Hover over this side tab to show the panel.

![auto hide][8]

## Save a Customized Layout

Once you apply any change in the panels position or size, the currently selected layout is switched to __Current__. This is the layout, which is used on the next start of Test Studio.

![Current layout][9]

You can save these current changes in the layout into a user defined layout. That way you will be able to switch to this at any time. Choose the __Save As__ option from the _Layouts_ dropdown.

![Save current into user defined layout][10]

You have two options in the __Save As__ dialog - to save the layout as a new user defined one, or to overwrite an existing one.

![Save current into new user defined layout][11]

If you choose to overwrite an existing user defined layout, there is a list with all available to choose from.

![Overwrite existing user defined layout][12]

The user defined layouts can be renamed, or deleted.

![Rename or Delete existing user defined layout][13]

> __Tip__
><br>
><br>
> To __reset the default project view__ you can switch to any of the predefined layouts. 

## See Also

- <a href="https://www.telerik.com/videos/teststudio/that-s-neat!-dockable-windows-in-test-studio">That’s neat! Dockable windows in Test Studio</q>

[1]: /img/automated-tests/customize-project/custom-layout/fig1.png
[2]: /img/automated-tests/customize-project/custom-layout/fig2.png
[2a]: /img/automated-tests/customize-project/custom-layout/fig2a.png
[2b]: /img/automated-tests/customize-project/custom-layout/fig2b.png
[2c]: /img/automated-tests/customize-project/custom-layout/fig2c.png
[3]: /img/automated-tests/customize-project/custom-layout/fig3.png
[4]: /img/automated-tests/customize-project/custom-layout/fig4.png
[4a]: /img/automated-tests/customize-project/custom-layout/fig4a.png
[5]: /img/automated-tests/customize-project/custom-layout/fig5.png
[6]: /img/automated-tests/customize-project/custom-layout/fig6.png
[7]: /img/automated-tests/customize-project/custom-layout/fig7.png
[8]: /img/automated-tests/customize-project/custom-layout/show-hidden-panel.gif
[9]: /img/automated-tests/customize-project/custom-layout/fig9.png
[10]: /img/automated-tests/customize-project/custom-layout/fig10.png
[11]: /img/automated-tests/customize-project/custom-layout/fig11.png
[12]: /img/automated-tests/customize-project/custom-layout/fig12.png
[13]: /img/automated-tests/customize-project/custom-layout/fig13.png

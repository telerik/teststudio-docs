---
title: Advanced Verification
page_title: Create Advanced Test Verifications
description: "Create Advanced Test Verifications in Test Studio test. Verify an element's attribute in Test Studio test"
previous_url: /user-guide/verifications/advanced-verification.aspx, /user-guide/verifications/advanced-verification, /features/verifications/advanced-verification
position: 1
---
# Create Advanced Test Verifications

An advanced verification allows you to interactively build verification rules and validate them against a live web document or WPF application.

In order to create custom verification you need to highlight the element and choose **Build Step...** from the menu:

![Build Step][1]

In the Recorder select **Verifications** node.

![Verifications][2]

Start by selecting a type of Available Verifications:

- IsVisible
- Content
- Attributes
- Style
- IsEnabled
- <a href="/features/recorder/verifications/image-verification" target="_blank">Image</a>

![Available verifications][3]

When crafting verifications, content is dynamically built against the currently selected element. As selections are made, default values are populated according to values the element contains.
For example, choose Content as the verification type and three menu options appear. 

![Content][4]

Click on the down arrow next to each option to see a list of possible values.

<table id="no-table">
<tr>
<td>![Inner Text][5]</td>
<td>![Exact][6]</td>
</tr>
<table>

Once finished building the verification(s), click **Add Step** to add it as a step to the current test.

![Add Step][7]

The newly created verification appears in the test:

![Test Steps][8]

> We recommend against using the Content Markup validation types. They are fragile in the face of minor page changes, and different browsers may reorder the element attributes making them unreliable. For more information please see our Automated Testing blog entry on <a href="http://blogs.telerik.com/jimholmes/posts/11-08-23/understanding-validation-content-element-types.aspx" target="_blank">**Understanding Validation Content Element Types**</a>. 

[1]: /img/features/recorder/verifications/advanced-verification/fig1.png
[2]: /img/features/recorder/verifications/advanced-verification/fig2.png
[3]: /img/features/recorder/verifications/advanced-verification/fig3.png
[4]: /img/features/recorder/verifications/advanced-verification/fig4.png
[5]: /img/features/recorder/verifications/advanced-verification/fig5.png
[6]: /img/features/recorder/verifications/advanced-verification/fig6.png
[7]: /img/features/recorder/verifications/advanced-verification/fig7.png
[8]: /img/features/recorder/verifications/advanced-verification/fig8.png
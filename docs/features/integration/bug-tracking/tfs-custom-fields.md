---
title: TFS Custom Fields
page_title: How to Submit a Bug to TFS with Custom Fields
description: "How to Submit a Bug from Test Studio to TFS with Custom Fields. Custom fields in the TFS issue/bug scheme supported in Test Studio."
previous_url: /user-guide/extensions/bug-tracking/tfs-custom-fields.aspx, /user-guide/extensions/bug-tracking/tfs-custom-fields
position: 1
---
# How to Submit a Bug to TFS with Custom Fields

Currently Test Studio does not support specifying custom fields through the UI when submitting a bug to TFS. If your customized TFS environment denotes certain fields as required before saving, you'll encounter an error when submitting a bug through Test Studio. Here's how to work-around this limitation:

1.&nbsp; Submit a bug to TFS through Test Studio. If it fails, you'll receive an error like this:

	*Unable to submit bug to Team Foundation Server. Error:*
	*BugTrackingName has an invalid value of NULL.*

![Error][1]

Where *BugTrackingName* is the name of the required field and *NULL* is its current (and invalid) value.

2.&nbsp; You should be able to confirm the required field by creating a bug directly in TFS and noting the required fields. Title and Description are automatically handled by Test Studio.

![New Bug][2]

3.&nbsp; To denote your required fields and what to fill them with, create a file called TFSMappings.xml in the following directory:

- For version 2012.2.920 and later: **C:\Program Files (x86)\Telerik\Test Studio\Bin\Plugins**
- For versions before 2012.2.920: **C:\Program Files (x86)\Telerik\Test Studio\Bin\Plugins\BugTrackers**

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

![Bug Trackers][3]

4.&nbsp; Open it with a text editor, like Notepad, and insert the following content:

```xml
<?xml version="1.0" encoding="utf-8"?>
<TFSMappings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <TemplateName>BugNew1</TemplateName>
  <Fields>
    <FieldMapping>
      <FieldName>BugTrackingName</FieldName>
      <FieldValue>NewName</FieldValue>
    </FieldMapping>
  </Fields>
</TFSMappings>
```

5.&nbsp; Submit the bug once again through Test Studio. It should succeed:

![Bug Submitted][4]

6.&nbsp; Open the bug in TFS and note the required field was filled in based on the XML file:

![Bug TFS][5]

[1]: /img/features/integration/bug-tracking/tfs-custom-fields/fig1.png
[2]: /img/features/integration/bug-tracking/tfs-custom-fields/fig2.png
[3]: /img/features/integration/bug-tracking/tfs-custom-fields/fig3.png
[4]: /img/features/integration/bug-tracking/tfs-custom-fields/fig4.png
[5]: /img/features/integration/bug-tracking/tfs-custom-fields/fig5.png
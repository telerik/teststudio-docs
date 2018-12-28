---
title: Import HTTP(S) Traffic
page_title: Import HTTP(S) Traffic
description: "Progress® Test Studio® for APIs - Import HTTP(S) Traffic"
position: 2
publish: true
---

# Import HTTP(S) Traffic

## Overview

With Progress® Test Studio® for APIs you can easily import a snapshot of your HTTP(S) traffic and create test steps against it.

The easiest way to capture HTTP(S) traffic is by using <a href="http://www.telerik.com/fiddler/web-traffic-recording">Fiddler</a>. You can store the HTTP(s) traffic you captured to an archive (<a href="http://fiddler.wikidot.com/saz-files">SAZ file</a>). This compressed file format contains the full request and response, as well as flags, timers, and other metadata. 

### Prerequisites

You need a Session Archive Zip (SAZ) file to complete the steps in this article. 

> You can use <a href="http://www.telerik.com/fiddler/fiddlercap">FiddlerCap</a> - a lightweight version of Fiddler designed solely for generating SAZ files. 

<br/>
> In order to import HTTPS sessions, you will need to enable the "Decrypt HTTPS traffic" option in Fiddler before you capture your requests. This way you will be able to export from Fiddler the raw, decrypted content of your sessions.
(To enable it go to: Tools > Telerik Fiddler Options > HTTPS > Decrypt HTTPS traffic in Fiddler and Capture Options Decrypt HTTPS traffic in FiddlerCap)

### Importing HTTP(S) Traffic

You can use the `Import Sessions` button located under Record main button at the top of Progress® Test Studio® for APIs.

![Import][1] 

A dialog will appear prompting you to locate the SAZ file containing the HTTP(S) traffic.

![Import][2]

Progress® Test Studio® for APIs will import the SAZ file and present you with its contents.

![Import][3]

### Creating test steps

You can now select individual session entries and add them to either an existing test step or to a new test case.
To do that, you can use the `Add Selected Sessions to Selected Test` and `Add Selected Sessions to a New Test` buttons.

![Import][4]

Progress® Test Studio® for APIs will import all the data associated with the session exchange entry.

> Note that `Content-Length` header will be skipped when importing a HTTP Request.

![Import][5] 

You can further extend the test step by adding verifications and conditions.

![Import][6] 

[1]: /img/features/import/import.png
[2]: /img/features/import/open-saz.png
[3]: /img/features/import/saz-contents.png
[4]: /img/features/import/session-exchange.png
[5]: /img/features/import/exchange-details.png
[6]: /img/features/import/conditions-and-verifications.png
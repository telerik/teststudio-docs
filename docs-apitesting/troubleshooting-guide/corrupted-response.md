---
title: Corrupted Response due to HTTP compression
page_title: Corrupted Response due to HTTP compression
description: "Progress® Test Studio® for APIs - Troubleshooting guide - Corrupted response due to HTTP compression"
position: 2
publish: true
---

# Corrupted Response due to HTTP compression

When you are <a href="/features/import/http-traffic">importing</a> or <a href="/features/record/http-traffic">recording</a> traffic, 
sometimes the request may contain an `Accept-Encoding` header that determines certain compression of the received response data. 
In this case the received data may seem corrupted in the UI of Test Studio for APIs. 
If you want to view the real content of the response, you should remove/delete the `Accept-Encoding` header as shown in the screenshot below.

> This suggestion is a temporary workaround. Built-in support for automatic response decompression is coming soon.

![Headers][1]

[1]: /img/troubleshooting-guide/request-headers/request-headers.png
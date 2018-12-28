---
title: Http Request Step Authorization
page_title: Http Request Step Authorization
description: "Progress® Test Studio® for APIs - Basic Authorization"
position: 2
---

# Http Request Step Authorization

> DEPRECATED

> This article is related to Test Studio for APIs version R3 2016 or older which do not yet have built-in support for authorization.

> For version R1 2017 or newer see [here](/features/steps/http-request#Authorization).  

You can enable Basic and OAuth authorization for any Http Request step by following the steps below.

## Basic

[Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) is the simplest technique for enforcing access controls to web resources. The mechanism provides no confidentiality protection for the transmitted credentials. The username and password are encoded with [Base64](https://en.wikipedia.org/wiki/Base64) and are added as a custom request header.

Create 3 new variables as shown below.

![Basic][1]

> `credentials-concatenated` is a variable that contains the `username` and `password` variables concatenated by a `:`

Add a <a href="/features/steps/set-variable">Set Variable</a> step that will transform the `credentials-concatenated` variable to a Base64 string and store it in a new variable called `credentials-encoded`

![Basic][2]

Add an <a href="/features/steps/http-request">Http Request</a> step and add an `Authorization` to the list of headers and set its value to `Basic {{credentials-encoded}}`.

![Basic][3]

## OAuth

Enabling OAuth authentication on a REST service api call can be achieved by combining Basic authentication and sending url encoded parameters using an `x-www-form-urlencoded` body.

1.Follow all the steps described in the Basic authentication section.

2.Add a new request header `Content-Type` and set its value to `application/x-www-form-urlencoded` 

![Basic][4]

3.Add all the necessary authentication parameters to the `Body` of the request. 

![Basic][5]

[1]: /img/features/authorization/variables.png
[2]: /img/features/authorization/encode-credentials.png
[3]: /img/features/authorization/authorization-header.png
[4]: /img/features/authorization/content-type.png
[5]: /img/features/authorization/url-encoded-body.png
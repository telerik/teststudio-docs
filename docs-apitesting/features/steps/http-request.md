---
title: Http Request Step
page_title: Http Request Step
description: "Progress® Test Studio® for APIs - Steps - Http Request Step"
position: 2
publish: true
---

# Http Request Step

## Overview

Use the HTTP Request Step to perform a single HTTP(S) request. After successful execution this Step will create the following <a href="/features/variables">Variables</a>: Body, Headers, StatusCode, ResponseTime, ReasonPhrase. This Step supports <a href="/features/verifications">Verifications</a> to make sure the HTTP Response is the same as the expected.

## Method

Specify HTTP Method for this request. You could choose one of the standard methods from the dropdown, or type a custom one if your application supports it.

> Test Studio for APIs supports custom methods.


## Url

Specify the URL for this request. The Url field supports <a href="/features/variables#Referencing-Variables">Variable References</a>.


## HTTPS

To make a HTTP or HTTPS request, simply set the corresponding protocol in the request URL (http:// or https://).

For HTTPS requests, Test Studio for APIs supports protocol versions from SSL 3.0 up to TLS 1.2. Test Studio for APIs will try to execute requests with the highest version that is supported by the server under test.

![Http Request Protocol][22]

**Note:** Older versions of Test Studio for APIs (2017.2.530.1 or earlier) support SSL 3.0 and TLS 1.0 only.

## Headers

Specify the HTTP headers for this request. You could choose one of the standard header names, or type a custom header if your application supports it. Both the Header Name and Value fields support <a href="/features/variables#Referencing-Variables">Variable References</a>.

> Use the Cookie Header to set cookies.



## Body

Specify the Body for this request. The Body field supports <a href="/features/variables#Referencing-Variables">Variable References</a>.

> The Body is not available for GET, HEAD and TRACE methods.

You can shape the data you want to send through the body of the request in 3 different ways.

#### raw

Raw request is the most basic way of sending data. The raw editor allows you format the data before sending it. Normally, you would be sending XML or JSON data.

> Test Studio for APIs doesn’t modify the string entered in the raw editor except replacing <a href="/features/variables#Referencing-Variables">variables</a>.

![Http Request Step][10]

Executing a step like the one above will result in the following.

![Http Request Step][11]

#### x-www-form-urlencoded

The key-value pairs you enter will be encoded properly and sent as URL parameters. Note that you can not upload files through this encoding mode.

![Http Request Step][12]

![Http Request Step][13]

#### form-data

Web forms use multipart/form-data to transfer data. Sending form data allows you simulate submitting a form to a website. Along with sending data as key-value pairs you can also upload files.
Any files selected for upload are copied in the test project and referred from there (files will be copied to {project_root}\\.files\\)

![Http Request Step][14]

Contents of the file.

![Http Request Step][15]

Result of submitting form data.

![Http Request Step][16]

### Formatting

You can format the contents of the Body by using the `Format` and `Wrap` buttons. Formatting can be applied to both `Request` and `Response`.

![Http Request Step][20]

## Authorization

You can enable Http Authentication for a given Http Request Step by using the `Authorization` tab. Currently supported Authorization modes are Basic and OAuth 2.0.

### Basic

[Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) is the simplest technique for enforcing access controls to web resources. 
The mechanism provides no confidentiality protection for the transmitted credentials. The username and password are encoded with Base64 and then added as a custom request header.

![Http Request Step][5]

> Clicking the `Update Request` button will add an `Authorization` header to the list of request headers.
>
>![Http Request Step][6] 

### OAuth 2.0

Test Studio for APIs provides a generic interface for [OAuth 2.0](https://tools.ietf.org/html/rfc6749) authorization. Users can achieve authorization against different OAuth 2.0 grant types simply by adding the desired properties to the "Body Content" form. The **supported grant types** are: password, client_credentials and refresh_token.

In the image below you can see a sample setup for **Resource owner credentials (password) grant**. To achieve authorization for **Client credentials (client_credentials) grant** for example, you would only need to use the "grant_type" and "scope" properties in the "Body Content" form and provide client_id and client_secret in the respective fields above.

![Http Request Step][7]

> Test Studio for APIs does not provide means for interaction with external user interface. This is why authorization flows that require the user to manually provide credentials (like **Authorisation Code Grant** or **Implicit grant**) are not supported. 

The values that you provide in the "Client Id" and "Client Secret" fields will be base64 encoded and added as a value to an "Authorization" header (with "Basic" prefix) in the http request (see the screenshot below). Currently, passing client_id and client_secret as an Authorization header is the only supported way to add them to the request. If you try to add them along with the rest of the parameters to the request body, Test Studio for APIs will still try to generate an Authorization header with the empty "Client Id" and "Client Secret" fields and this will lead to incorrect request header.

> Clicking the `Update Request` button will:
> 
> 1. Add an `Authorization` header to the list of request headers. Its value will be a Base64 encoding of the `client_id:client_secret`
> 2. Add a `Content-Type` header to the list of request headers. Its value will be set to `application/x-www-form-urlencoded`
> ![Http Request Step][8]
>
> 3. Add all the key/value pairs from the `Body Content` section to the `Body` section of the request.
> 
> ![Http Request Step][9]

If you want to learn more about the OAuth 2.0 authorization flows, you can examine the list below.

* [Resource Owner Credentials Grant](https://tools.ietf.org/html/rfc6749#section-1.3.3)
 
* [Client Credentials Grant](https://tools.ietf.org/html/rfc6749#section-1.3.4)

* [Refresh Token](https://tools.ietf.org/html/rfc6749#section-1.5)


## Settings 

### Specify Timeout for this request. 

> The default Timeout is 2000ms.

### Follow redirects

> If Follow Redirects is set to false, all responses with an HTTP status code from 300 to 399 is returned to the application. The default value is true.

### Decompress Reponse

By default, Progress® Test Studio® for APIs will attempt to decompress http responses that contain a **"Content-Encoding"** response header with value **gzip** or **deflate**. 

> If the response's **"Content-Encoding"** header includes both **gzip** and **deflate** options, Progress® Test Studio® for APIs will attempt to apply both decompressions in the order they are specified in the header's value. Other encoding types are not supported.

If you wish to disable response decompression, you can uncheck the **Decompress response** checkbox in the http request's **Settings**

![Decompress response Setting][21]

## Response Data

After successful execution Test Studio for APIs will display specialized UI to preview the values of the Step <a href="/features/variables">Variables</a>.

> You could use the `+` buttons next to the response Headers, Status Code and Response Time to easily add <a href="/features/verifications">Verifications</a>. 
> ![Http Request Step][17]

The `Last Response Data` section is where you'll preview the result of an Http Request step. If you request an image, Test Studio for APIs will display it in the `Body` section. 
You can perform additional action on the image such as opening it in the default image viewer or saving it on the file system.

![Http Request Step][18]

For text-based files you have the option to format their contents as `Raw`, `JSON` or `XML`.

![Http Request Step][19]

[1]: /img/features/steps/http-request.png
[2]: /img/features/steps/http-response.png
[3]: /img/features/steps/http-request-body-format-raw.png
[4]: /img/features/steps/http-request-body-format-json.png
[5]: /img/features/steps/http-request/http-request-basic.png
[6]: /img/features/steps/http-request/http-request-basic-headers.png
[7]: /img/features/steps/http-request/http-request-oauth.png
[8]: /img/features/steps/http-request/http-request-oauth-headers.png
[9]: /img/features/steps/http-request/http-request-oauth-body.png
[10]: /img/features/steps/http-request/body/body-raw.png
[11]: /img/features/steps/http-request/body/body-raw-response.png
[12]: /img/features/steps/http-request/body/body-x-www-form-urlencoded.png
[13]: /img/features/steps/http-request/body/body-x-www-form-urlencoded-response.png
[14]: /img/features/steps/http-request/body/body-form-data.png
[15]: /img/features/steps/http-request/body/body-form-data-test-file.png
[16]: /img/features/steps/http-request/body/body-form-data-response.png
[17]: /img/features/steps/http-request/http-request-response.png
[18]: /img/features/steps/http-request/http-request-response-image.png
[19]: /img/features/steps/http-request/http-request-response-json.png
[20]: /img/features/steps/http-request/http-request-formatting.png
[21]: /img/features/steps/http-request/decompress-response-http-setting.png
[22]: /img/features/steps/http-request/http-request-protocol.png

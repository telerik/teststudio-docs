---
title: Troubleshooting Login Issues on Telerik Website
description: Users might experience difficulties signing into their Telerik accounts due to the CloudFlare verification with error "Oops! We couldn't verify you're human. Please try a different browser or contact us for assistance." Anyone with the issue can try these steps to troubleshoot the issue and find a workaround.
type: troubleshooting
page_title: How to Resolve Login Problems on Telerik.com
slug: login-issues-telerik-website
tags: progress, telerik, test studio, login, troubleshooting
res_type: kb
ticketid: 1661389
position: 19
---

## Description

When attempting to sign into the Telerik website errors may appear in the browser console due to the CloudFlare verification. The error in the browser is as follows: 

````HTML
Oops! We couldn't verify you're human. Please try a different browser or contact us for assistance. 
````

![Login error](/img/knowledge-base/telerik-login-kb/fig1.png)

The issue persists across different browsers and devices. Clearing the browser's cache or using incognito mode might temporarily allow for successful login, but the problem reoccurs.

## Cause

This issue can arise from various browser-related problems. These include outdated browser versions, stored cache and cookies, disabled JavaScript or cookies, active browser extensions, or network restrictions.

## Solution

To troubleshoot and potentially resolve login issues on the Telerik website, follow these steps:

1. Ensure the used browser is up-to-date. Check the browser's official website for information on the latest version and update if necessary.
2. Clear the browser's cache and cookies. This step removes saved website data that might be causing the issue.
3. Disable all browser extensions including Test Studio Extension. Extensions can interfere with website functionality, including login processes.
4. Confirm that JavaScript is enabled in the browser settings. JavaScript is essential for many website interactions.
5. Ensure that cookies are enabled. Cookies are necessary for maintaining a login session.
6. Try accessing the website again __using incognito or private browsing mode__. This mode uses a fresh session without saved cookies or cache.
7. Test the login process with a __different browser or device__ to rule out browser-specific issues.
8. Attempt to __access the website from a different network__. Some networks may have restrictions that impact website functionality.



## See Also

- [How to Enable JavaScript in Your Browser](https://www.enable-javascript.com/)
- [How to Clear Cache and Cookies in Major Browsers](https://www.pcworld.com/article/242939/how-to-delete-cookies.html)

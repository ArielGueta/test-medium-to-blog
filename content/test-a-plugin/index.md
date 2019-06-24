---
title: "Test a Plugin"
description: "This page describes Angular’s built-in protections against common web-application vulnerabilities and attacks such as cross-site scripting attacks. It doesn’t cover application-level security, such…"
date: "2019-06-24T13:14:24.181Z"
categories: 
  - Security

published: true
canonical_link: https://medium.com/@angularavel/test-a-pluginsecurity-d7b7010d301f
redirect_from:
  - /test-a-pluginsecurity-d7b7010d301f
---

### Security

This page describes Angular’s built-in protections against common web-application vulnerabilities and attacks such as cross-site scripting attacks. It doesn’t cover application-level security, such as authentication (_Who is this user?_) and authorization (_What can this user do?_).

For more information about the attacks and mitigations described below, see [OWASP Guide Project](https://www.owasp.org/index.php/Category:OWASP_Guide_Project).

You can run the [live example](https://angular.io/generated/live-examples/security/stackblitz.html "live example") / [download example](https://angular.io/generated/zips/security/security.zip "Download example") in Stackblitz and download the code from there.

<Embed src="https://gist.github.com/ArielGueta/b13bec2b35efb234bf7be1b77ae26b7f.js" aspectRatio={0.357} caption="" />

Interpolated content is always escaped — the HTML isn’t interpreted and the browser displays angle brackets in the element’s text content.

For the HTML to be interpreted, bind it to an HTML property such as `innerHTML`. But binding a value that an attacker might control into `innerHTML` normally causes an XSS vulnerability. For example, code contained in a `<script>` tag is executed:

<Embed src="https://gist.github.com/ArielGueta/0fc416f2b512fea6fb06625ccb7c11bd.js" aspectRatio={0.357} caption="" />

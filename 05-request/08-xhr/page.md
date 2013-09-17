---
title: XMLHttpRequest
status: live
---

When using a Javascript framework like MooTools or jQuery to execute an XMLHttpRequest, the XMLHttpRequest will
usually be sent with a **X-Requested-With** HTTP header. The Slim application will detect the HTTP
request’s **X-Requested-With** header and flag the request as such. If for some reason an XMLHttpRequest cannot
be sent with the **X-Requested-With** HTTP header, you can force the Slim application to assume an HTTP request
is an XMLHttpRequest by setting a GET, POST, or PUT parameter in the HTTP request named “isajax” with a truthy value.

Use the request object's `isAjax()` or `isXhr()` method to ttell if the current request is an XHR/Ajax request:

    <?php
    $isXHR = $app->request()->isAjax();
    $isXHR = $app->request()->isXhr();

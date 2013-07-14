---
title: Request Headers
status: live
---

A Slim application will automatically parse all HTTP request headers. You can access the request headers using the
request object's `headers()` method.

    <?php
    $app = new \Slim\Slim();

    // Get request object
    $req = $app->request();

    // Get request headers as associative array
    $headers = $req->headers();

    // Get the ACCEPT_CHARSET header
    $charset = $req->headers('ACCEPT_CHARSET');

In the second example, the `headers()` method will either return a string value or `null` if the header with the
given name does not exist.

The HTTP specification states that HTTP header names may be uppercase, lowercase, or mixed-case. Slim is smart enough
to parse and return header values whether you request a header value using upper, lower, or mixed case header name,
with either underscores or dashes. So use the naming convention with which you are most comfortable.

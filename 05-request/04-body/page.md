---
title: Request Body
status: live
---

Use the request object's `getBody()` method to fetch the raw HTTP request body sent by the HTTP client. This is
particularly useful for Slim application's that consume JSON or XML requests.

    <?php
    $request = $app->request();
    $body = $request->getBody();

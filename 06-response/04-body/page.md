---
title: Response Body
status: live
---

The HTTP response returned to the client will have a body. The HTTP body is the actual content of the HTTP response
delivered to the client. You can use the Slim application’s response object to set the HTTP response’s body:

    <?php
    $res = $app->response();

    // Overwrite response body
    $res->body('Foo');

    // Append response body
    $res->write('Bar');

When you overwrite or append the response object’s body, the response object will automatically set the
**Content-Length** header based on the bytesize of the new response body.

You can fetch the response object’s body using the same `body()` method without an argument:

    <?php
    $res = $app->response();
    $body = $res->body();

Usually, you will never need to manually set the response body with the `body()` or `write()` methods; instead,
the Slim application will do this for you. Whenever you `echo()` content inside a route's callback function, the
`echo()`’d content is captured in an output buffer and appended to the response body before the HTTP response
is returned to the client.

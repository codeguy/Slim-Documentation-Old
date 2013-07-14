---
title: Response Headers
status: live
---


The HTTP response returned to the HTTP client will have a header. The HTTP header is a list of keys and values that
provide metadata about the HTTP response. You can use the Slim application’s response object to set the HTTP
response’s header. The response object is special because it acts like an array:

    <?php
    $res = $app->response();
    $res['Content-Type'] = 'application/json';
    $res['X-Powered-By'] = 'Slim';

You may also fetch headers from the response object:

    <?php
    $res = $app->response();
    $contentType = $response['Content-Type'];
    $poweredBy = $response['X-Powered-By'];

If a header with the given name does not exist, `null` is returned. You may specify header names with upper, lower,
or mixed case with dashes or underscores. Use the naming convention with which you are most comfortable.

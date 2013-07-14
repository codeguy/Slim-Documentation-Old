---
title: Request Variables
status: live
---

An HTTP request may have associated variables (not to be confused with route variables). The GET, POST, or PUT
variables sent with the current HTTP request are exposed via the Slim application’s request object.

If you want to quickly fetch a request variable value without considering its type, use the request object's `params()`
method:

    <?php
    $req = $app->request();
    $paramValue = $req->params('paramName');

The `params()` method will first search PUT variables, then POST variables, then GET variables. If no variables
are found, `null` is returned. If you only want to search for a specific type of variable, you can use these
methods instead:

    <?php
    // Get request object
    $req = $app->request();

    //GET variable
    $paramValue = $req->get('paramName');

    //POST variable
    $paramValue = $req->post('paramName');

    //PUT variable
    $paramValue = $req->put('paramName');

If a variable does not exist, each method above will return `null`. You can also invoke any of these functions without
an argument to obtain an array of all variables of the given type:

    <?php
    $req = $app->request();
    $allGetVars = $req->get();
    $allPostVars = $req->post();
    $allPutVars = $req->put();

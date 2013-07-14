---
title: Activate Logging
status: live
---

The Slim application’s log object provides the following public methods to enable or disable logging during runtime.

    <?php
    //Enable logging
    $app->getLog()->setEnabled(true);

    //Disable logging
    $app->getLog()->setEnabled(false);

You may enable or disable the log object during application instantiation like this:

    <?php
    $app = new Slim(array(
        'log.enabled' => true
    ));

If logging is disabled, the log object will ignore all logged messages until it is enabled.

---
title: Overview
status: live
---

A Slim application provides a log object that writes data to a specific output. The actual writing of data is
delegated to a log writer.

### How to log data

To log data in a Slim application, get a reference to the log object:

    <?php
    $log = $app->getLog();

The log object provides the following interface:

    $log->debug(mixed $object);
    $log->info(mixed $object);
    $log->warn(mixed $object);
    $log->error(mixed $object);
    $log->fatal(mixed $object);

Each log object method accepts one mixed argument. The argument is usually a string, but the argument can be
anything. The log object will pass the argument to its log writer. It is the log writer’s responsibility to write
arbitrary input to the appropriate destination.

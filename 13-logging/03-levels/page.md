---
title: Log Levels
status: live
---

<div class="alert alert-info">
    <strong>Heads Up!</strong> Use the <code>\Slim\Log</code> constants when setting the log level instead
    of using raw integers.
</div>

The Slim application’s log object will respect or ignore logged messages based on its log level setting. When you
invoke the log objects’s `debug()`, `info()`, `warn()`, `error()`, or `fatal()` methods, you are inherently assigning
a level to the logged message. The available log levels are:

\Slim\Log::DEBUG
: Level 4

\Slim\Log::INFO
: Level 3

\Slim\Log::WARN
: Level 2

\Slim\Log::ERROR
: Level 1

\Slim\Log::FATAL
: Level 0

Only messages that have a level less than the current log object’s level will be logged. For example, if the log
object’s level is `\Slim\Log::WARN` (2), the log object will ignore `\Slim\Log::DEBUG` and `\Slim\Log::INFO` messages
but will accept `\Slim\Log::WARN`, `\Slim\Log::ERROR`, and `\Slim\Log::FATAL` messages.

### How to set the log level

    <?php
    $log = $app->getLog();
    $log->setLevel(\Slim\Log::WARN);

You can set the log object’s level during application instantiation, too:

    <?php
    $app = new \Slim\Slim(array(
        'log.level' => \Slim\Log::WARN
    ));

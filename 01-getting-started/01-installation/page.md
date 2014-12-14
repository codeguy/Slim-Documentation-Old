---
title: Installation
status: live
---

### Composer Install

Install composer in your project:

    curl -s https://getcomposer.org/installer | php

Add the Slim framework as a dependency:

    composer require "slim/slim"

Add this line to your application's `index.php` file:

    <?php
    require 'vendor/autoload.php';

### Manual Install

Download and extract the Slim Framework into your project directory and `require` it in your application's `index.php`
file. You'll also need to register Slim's autoloader.

    <?php
    require 'Slim/Slim.php';
    \Slim\Slim::registerAutoloader();

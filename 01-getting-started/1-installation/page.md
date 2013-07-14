---
title: Installation
status: live
---

### Composer Install

Install composer in your project:

    curl -s https://getcomposer.org/installer | php

Create a `composer.json` file in your project root:

    {
        "require": {
            "slim/slim": "2.*"
        }
    }

Install via composer:

    php composer.phar install

Add this line to your application's `index.php` file:

    <?php
    require 'vendor/autoload.php';

### Manual Install

Download and extract the Slim Framwork into your project directory and `require` it in your application's `index.php`
file. You'll also need to register Slim's autoloader.

    <?php
    require 'Slim/Slim.php';
    \Slim\Slim::registerAutoloader();

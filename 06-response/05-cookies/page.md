---
title: Response Cookies
status: live
---

The Slim application provides helper methods to send cookies with the HTTP response.

### Set Cookie

This example demonstrates how to use the Slim application’s `setCookie()` method to create an HTTP cookie to be sent
with the HTTP response:

    <?php
    $app->setCookie('foo', 'bar', '2 days');

This creates an HTTP cookie with the name "foo" and value "bar" that expires two days from now. You may also provide
additional cookie properties, including its path, domain, secure, and httponly settings. The Slim application’s
`setCookie()` method uses the same signature as PHP’s native `setCookie()` function.

    <?php
    $app->setCookie(
        $name,
        $value,
        $expiresAt,
        $path,
        $domain,
        $secure,
        $httponly
    );

### Set Encrypted Cookie

You may also create encrypted cookies using the Slim application’s `setEncryptedCookie()` method. This method acts
the same as the Slim application’s `setCookie()` method demonstrated above, but it will encrypt the cookie value
using the AES–256 cipher and your own secret key. To use encryption, you must define your encryption key when you
instantiate your Slim application like this:

    <?php
    $app = new \Slim\Slim(array(
        'cookies.secret_key' => 'my_secret_key'
    ));

If you prefer, you may change the default cipher and cipher mode, too:

    <?php
    $app = new \Slim\Slim(array(
        'cookies.secret_key' => 'my_secret_key',
        'cookies.cipher' => MCRYPT_RIJNDAEL_256,
        'cookies.cipher_mode' => MCRYPT_MODE_CBC
    ));

The encrypted cookie value is hashed and later verified to ensure data integrity so that its value is not changed
while on the HTTP client.

### Delete Cookie

You can delete a cookie using the Slim application’s `deleteCookie()` method. This will remove the cookie from
the HTTP client before the next HTTP request. This method accepts the same signature as the Slim application’s
`setCookie()` instance method, *without* the `$expires` argument. Only the first argument is required.

    <?php
    $app->deleteCookie('foo');

If you need to also specify the path and domain:

    <?php
    $app->deleteCookie('foo', '/', 'foo.com');

You may also further specify the secure and httponly properties:

    <?php
    $app->deleteCookie('foo', '/', 'foo.com', true, true);

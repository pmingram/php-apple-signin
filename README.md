php-apple-signin Apple 苹果账号登陆
=======
PHP library to manage Sign In with Apple identifier tokens, and validate them server side passed through by the iOS client.

PHP库来管理使用Apple标识符令牌的登录，并验证iOS客户端通过的服务器端。

Installation 安装
------------

Use composer to manage your dependencies and download php-apple-signin:

需要您的项目使用 composer 管理依赖，使用下方命令安装此库。

```bash
composer require yanlongli/php-apple-signin
```

Example
-------
```php
<?php
use AppleSignIn\ASDecoder;
// ASAuthorizationAppleIDCredential credential
$clientUser = "example_client_user"; //credential.user
$identityToken = "example_encoded_jwt"; // credential.identityToken

$appleSignInPayload = ASDecoder::getAppleSignInPayload($identityToken);

/**
 * Obtain the Sign In with Apple email and user creds.
 */
$email = $appleSignInPayload->getEmail();
$user = $appleSignInPayload->getUser();

/**
 * Determine whether the client-provided user is valid.
 */
$isValid = $appleSignInPayload->verifyUser($clientUser);

?>
```

# FAQ

[FAQ](doc/faq.md)

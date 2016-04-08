Yii 2 Practical-B Application Template
======================================

[![Latest Stable Version](https://poser.pugx.org/kartik-v/yii2-app-practical-b/v/stable.svg)](https://packagist.org/packages/kartik-v/yii2-app-practical-b) 
[![License](https://poser.pugx.org/kartik-v/yii2-app-practical-b/license.svg)](https://packagist.org/packages/kartik-v/yii2-app-practical-b)
[![Total Downloads](https://poser.pugx.org/kartik-v/yii2-app-practical-b/downloads.svg)](https://packagist.org/packages/kartik-v/yii2-app-practical-b) 
[![Monthly Downloads](https://poser.pugx.org/kartik-v/yii2-app-practical-b/d/monthly.png)](https://packagist.org/packages/kartik-v/yii2-app-practical-b)
[![Daily Downloads](https://poser.pugx.org/kartik-v/yii2-app-practical-b/d/daily.png)](https://packagist.org/packages/kartik-v/yii2-app-practical-b)

The Yii 2 Practical-B Application Template is a skeleton Yii 2 application based on the 
[yii2-basic template](https://github.com/yiisoft/yii2-app-basic/) best for
rapidly creating small projects. The template allows a **practical** method to directly 
access the application from the app root.

The template contains the basic features including user login/logout and a contact page.
It includes all commonly used configurations that would allow you to focus on adding new
features to your application.


Why yii2-practical-b?
---------------------

After installing a `app`, in the yii2-basic application you normally would access the
frontend by:

```
http://domain/app/web
```

However, in many **practical** scenarios (especially on shared and single domain hosts) one 
would want their users to directly access the app as:

```
http://domain/app
```

The `yii2-app-practical-b` enables you to achieve just that by carefully moving and rearranging the 
bootstrap files and web components of frontend to work directly out of the app root. The 
`web` folder is entirely eliminated and one can directly access the application frontend
this way:

```
http://domain/app
```

All other aspects of the app configuration remain the same as the **yii2-basic** app. The original `assets` folder
in the approot is renamed to `assets_b`, while the `web/assets` folder moves to app root.

SOME KEY ADDITIONS
-------------------

1. The template has some security preconfigured for users with Apache web servers. It has a default `.htaccess` security configuration setup.
2. The template has prettyUrl enabled by default and the changes have been made to `.htaccess` as well as `urlManager`
   component config in the config directory.

DIRECTORY STRUCTURE
-------------------

```
    /                   contains the entry script and web resources
    assets/             contains the web runtime assets
    assets_b/           contains application assets such as JavaScript and CSS
    commands/           contains console commands (controllers)
    config/             contains application configurations
    controllers/        contains Web controller classes
    mail/               contains view files for e-mails
    models/             contains model classes
    runtime/            contains files generated during runtime
    tests/              contains various tests for the yii2-practical-b application
    vendor/             contains dependent 3rd-party packages
    views/              contains view files for the Web application
```

REQUIREMENTS
------------

The minimum requirement by this application template that your Web server supports PHP 5.4.0.


INSTALLATION
------------

### Install from an Archive File

Extract the archive file downloaded from [yiiframework.com](http://www.yiiframework.com/download/) to
a directory named `practical-b` that is directly under the Web root.

> Note: When using a archive file method, the vendor folder is not automatically created. You must 
 extract the [yii2-basic vendor folder from here](https://github.com/yiisoft/yii2/releases/download/2.0.0/yii-basic-app-2.0.0.tgz).
 Then you must copy this folder directly under the app root (i.e. `practical-b` directory).
 
Set cookie validation key in `config/web.php` file to some random secret string:

```php
'request' => [
    // !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
    'cookieValidationKey' => '<secret random string goes here>',
],
```

You can then access the application through the following URL:

~~~
http://localhost/practical-b/
~~~


### Install via Composer

If you do not have [Composer](http://getcomposer.org/), you may install it by following the instructions
at [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix).

You can then install this application template using the following command:

~~~
php composer.phar global require "fxp/composer-asset-plugin:1.0.0"
php composer.phar create-project --prefer-dist --stability=dev kartik-v/yii2-app-practical-b practical-b
~~~

Now you should be able to access the application through the following URL, assuming `practical-b` is the directory
directly under the Web root.

~~~
http://localhost/practical-b
~~~


CONFIGURATION
-------------

### Database

Edit the file `config/db.php` with real data, for example:

```php
return [
	'class' => 'yii\db\Connection',
	'dsn' => 'mysql:host=localhost;dbname=yii2practicalb',
	'username' => 'root',
	'password' => '1234',
	'charset' => 'utf8',
];
```

**NOTES:**
- Yii won't create the database for you, this has to be done manually before you can access it.
- Check and edit the other files in the `config/` directory to customize your application as required.
- Refer to the README in the `tests` directory for information specific to basic application tests.
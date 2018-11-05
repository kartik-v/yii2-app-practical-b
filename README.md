<h1 align="center">
    <a href="http://demos.krajee.com" title="Krajee Demos" target="_blank">
        <img src="http://kartik-v.github.io/bootstrap-fileinput-samples/samples/krajee-logo-b.png" alt="Krajee Logo"/>
    </a>
    <br>
    Yii 2 Practical-B Project Template
    <hr>
    <a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=DTP3NZQ6G2AYU"
       title="Donate via Paypal" target="_blank">
        <img src="http://kartik-v.github.io/bootstrap-fileinput-samples/samples/donate.png" alt="Donate"/>
    </a>
</h1>

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

The minimum requirement by this project template that your Web server supports PHP 5.4.0.


INSTALLATION
------------

### Install via Composer

If you do not have [Composer](http://getcomposer.org/), you may install it by following the instructions
at [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix).

You can then install this project template using the following command:

~~~
php composer.phar global require "fxp/composer-asset-plugin:^1.3.1"
php composer.phar create-project --prefer-dist --stability=dev kartik-v/yii2-app-practical-b practical-b
~~~

Now you should be able to access the application through the following URL, assuming `practical-b` is the directory
directly under the Web root.

~~~
http://localhost/practical-b
~~~

### Install from an Archive File

Extract the archive file downloaded from [yiiframework.com](http://www.yiiframework.com/download/) to
a directory named `basic` that is directly under the Web root.

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


CONFIGURATION
-------------

### Database

Edit the file `config/db.php` with real data, for example:

```php
return [
    'class' => 'yii\db\Connection',
    'dsn' => 'mysql:host=localhost;dbname=yii2basic',
    'username' => 'root',
    'password' => '1234',
    'charset' => 'utf8',
];
```

**NOTES:**
- Yii won't create the database for you, this has to be done manually before you can access it.
- Check and edit the other files in the `config/` directory to customize your application as required.
- Refer to the README in the `tests` directory for information specific to basic application tests.

TESTING
-------

Tests are located in `tests` directory. They are developed with [Codeception PHP Testing Framework](http://codeception.com/).
By default there are 3 test suites:

- `unit`
- `functional`
- `acceptance`

Tests can be executed by running

```
vendor/bin/codecept run
``` 

The command above will execute unit and functional tests. Unit tests are testing the system components, while functional
tests are for testing user interaction. Acceptance tests are disabled by default as they require additional setup since
they perform testing in real browser. 


### Running  acceptance tests

To execute acceptance tests do the following:  

1. Rename `tests/acceptance.suite.yml.example` to `tests/acceptance.suite.yml` to enable suite configuration

2. Replace `codeception/base` package in `composer.json` with `codeception/codeception` to install full featured
   version of Codeception

3. Update dependencies with Composer 

    ```
    composer update  
    ```

4. Download [Selenium Server](http://www.seleniumhq.org/download/) and launch it:

    ```
    java -jar ~/selenium-server-standalone-x.xx.x.jar
    ```

    In case of using Selenium Server 3.0 with Firefox browser since v48 or Google Chrome since v53 you must download [GeckoDriver](https://github.com/mozilla/geckodriver/releases) or [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) and launch Selenium with it:

    ```
    # for Firefox
    java -jar -Dwebdriver.gecko.driver=~/geckodriver ~/selenium-server-standalone-3.xx.x.jar
    
    # for Google Chrome
    java -jar -Dwebdriver.chrome.driver=~/chromedriver ~/selenium-server-standalone-3.xx.x.jar
    ``` 
    
    As an alternative way you can use already configured Docker container with older versions of Selenium and Firefox:
    
    ```
    docker run --net=host selenium/standalone-firefox:2.53.0
    ```

5. (Optional) Create `yii2_basic_tests` database and update it by applying migrations if you have them.

   ```
   tests/bin/yii migrate
   ```

   The database configuration can be found at `config/test_db.php`.


6. Start web server:

    ```
    tests/bin/yii serve
    ```

7. Now you can run all available tests

   ```
   # run all available tests
   vendor/bin/codecept run

   # run acceptance tests
   vendor/bin/codecept run acceptance

   # run only unit and functional tests
   vendor/bin/codecept run unit,functional
   ```

### Code coverage support

By default, code coverage is disabled in `codeception.yml` configuration file, you should uncomment needed rows to be able
to collect code coverage. You can run your tests and collect coverage with the following command:

```
#collect coverage for all tests
vendor/bin/codecept run -- --coverage-html --coverage-xml

#collect coverage only for unit tests
vendor/bin/codecept run unit -- --coverage-html --coverage-xml

#collect coverage for unit and functional tests
vendor/bin/codecept run functional,unit -- --coverage-html --coverage-xml
```

You can see code coverage output under the `tests/_output` directory.

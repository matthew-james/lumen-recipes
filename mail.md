# Mail

The iiluminate/mail package was removed in Lumen 5.2.  You will need to manually add it to send emails in Lumen 5.2+.

## Installation

First you need to require the composer package.  Run the following command from the terminal to add the mail package to your composer.json.

```
composer require "illuminate/mail:5.2.*"
```

## Configuration

The service provider expects a configuration file to exist.  The following lines will create the config directory if it does not exist and copy a fresh configuration file from the full Laravel framework.

```
mkdir -p config
curl -o config/mail.php https://raw.githubusercontent.com/laravel/laravel/v5.2.0/config/mail.php
```

## Registration

Next you need to register the service provider with your application and tell Lumen to load your config.  The following lines should be added to `bootstrap/app.php`.

```php
$app->register(Illuminate\Mail\MailServiceProvider::class);
$app->configure('mail');
```

## Facade

If you would like to use the facade, make sure you have enabled facades by uncommenting the `$app->withFacades()` line in `bootstrap/app.php`.  Next, add the following code to register the Mail facade.

```php
if( ! class_exists('Mail') ) {
    class_alias(Illuminate\Support\Facades\Mail::class, 'Mail');
}
```

- contributed by [dpearre](https://github.com/dpearre)

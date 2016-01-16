# Tinker

The `php artisan tinker` command from Laravel is not available in Lumen, so you will need to add it manually.

## Installation

First you need to require the [psysh](http://psysh.org/) composer package.  Run the following command from the terminal to add the psysh package to your composer.json.

```
composer require psy/psysh:@stable
```

## Command

You need to add an artisan command to launch the psysh shell.  Run the following command to copy the TinkerCommand class into your application.

```
curl -o app/Console/Commands/TinkerCommand.php https://raw.githubusercontent.com/matthew-james/lumen-recipes/master/TinkerCommand.php
```

## Registration

Next you need to register the Command with your application.  The TinkerCommand class name should be added to `app/Console/Kernel.php`.

```php
protected $commands = [
  // your other commands...
  Commands\TinkerCommand::class
];
```
